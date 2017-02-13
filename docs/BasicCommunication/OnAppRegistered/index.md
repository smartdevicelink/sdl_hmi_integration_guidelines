## OnAppRegistered

Type
: Notification

Sender
: SDL

Purpose
: Update the HMI's list of registered applications and resume the Audio Source

SDL will send `OnAppRegistered`:

  1. After an SDL-enabled application has registered successfully.
  2. When the device was reconnected after an unexpected disconnect and a previously connected SDL application reregisters. SDL makes a decision if the data resumption process is applicable for the application.
  3. When the HMI sends an `OnFindApplications` notification via the users request.

Regarding data resumption:

Data resumption means that an app may request to restore data used in the previous ignition cycle after an `Unexpected Disconnect`.


  * For data resumption purposes, SDL must store application-related data such as commands, application global properties, and show data for the past three ignition cycles after an `Unexpected Disconnect` or `Ignition Off`. On the fourth  `Ignition On`, SDL clears all corresponding application-related data used for resumption.
  * HMI must store the VR grammar compiled for applications that are unregistered by an `Unexpected Disconnect` or `Ignition Off`.
  * During data resumption, the HMI may also have to resume the previous audio source. Refer to `BC.OnResumeAudioSource`.

If the application resumes data successfully:

  * SDL will provide `OnAppRegistered` with `resumeVrGrammars`:`true` to notify the HMI that `VRGrammars` must be resumed. On this event, the HMI must restore the application related `VRGgrammars` for the appID received via an `OnAppRegistered` notification.
  * SDL must restore application-related data and send to the HMI after an `OnAppRegistered` notification:
    * `AddCommand`(Menu + VR)
    * `AddSubMenu`
    * `CreateInteractionChoiceSet`
    * `SetGlobalProperties`
    * `SubscribeButton`
    * `SubscibeVehicleData`

If the application does not resume data successfully:

  * SDL will provide `OnAppRegistered` with `resumeVrGrammars`:`false` or no resume parameter at all.
  * SDL cleans up all previously stored application data for the application that failed to resume. The HMI must also clean up previously compiled `VRGrammars` for the application.
  * The application will send new data to start SDL operations. In this event, SDL and the HMI should restart the cycle of collecting application data for resumption.

!!! MUST

  1. HMI must update its list of registered applications.
  2. HMI must store the application data sent in the `applications` parameter.
  3. HMI must compile and store `VRGrammars` for the `vrSynonyms` parameter, and arrange them for the user to be able to use via voice recognition. Note: The VR commands to activate an application must be accessible when viewing a different active application or the list of registered applications.
  4. HMI must provide the user with the possibility to choose an application among a list of registered applications.
  5. HMI must send an `OnAppActivated` notification to SDL when the user activates an app via the `UI` or `VR`.

!!!

!!! NOTE

If a device is connected over USB and registers an application, SDL will send `OnAppRegistered` with a hash of the usb serial number as the device id.

If a device is connected over Bluetooth or Wi-Fi and registers an application, SDL will send `OnAppRegistered` with a hash of the device's mac address as the device id.

!!!


###The below describes the behavior related to RSDL functionality only.   

_**Changes**_   
  1.	New appHMIType: REMOTE_CONTROL was added: all and any remote-control applications must register with this type.   
  2.	Registration of identical applications (that is, with the same name, same VRSynonyms, same policies_appID), one from driver's device and another one from passenger's device, is allowed by RSDL.   
  3.	Passenger's applications are not allowed to be activated to FULL level.   
  
_**Behavior**_

i. _Application from driver's device registers_ - the vehicle must:   
     1.	Know the device rank is driver's (see also [RC.OnDevcieRankChanged]).   
     2.	Mark each application registered from driver's device with "D - \<appName>" when displaying in the list of registered applications (all required information comes from _BasicCommunication.OnAppRegistered_).   
     3.	Send _SDL.ActivateApp_ to RSDL in case the driver activates such application through either UI or VR.   
     4.	Send _OnExitApplication(USER_EXIT)_ in case the driver decides to exit such application through either UI or VR.

[RC.OnDevcieRankChanged]: https://github.com/smartdevicelink/sdl_hmi_integration_guidelines/blob/feature/docs/RC/RC.OnDeviceRankChanged/index.md


II. _Application from passenger's device registers_ - the vehicle must:
     1.	Know the device rank is passenger's (see also [RC.OnDevcieRankChanged]).   
     2.	Display _only applications in LIMITED_ level (meaning, only passenger's applications that received driver's permission to remotely control. RSDL notifies about changed HMILevel via _BasicCommunication.ActivateApp_("level"), see [6.2 ActivateApp of SDL Integration Guidelines]).   
     3.	In case displayed, mark each application registered from passenger's device with "P - \<appName>".   
     4.	Ignore passenger's application _VRSynonyms_ in case the identical driver's application is also registered.   
     5.	Never allow to activate passenger's application.   
     6.	Allow only "User Exit" for passenger's application (see [6.15 OnExitApplication of SDL Integration Guidelines]).

[RC.OnDevcieRankChanged]: https://github.com/smartdevicelink/sdl_hmi_integration_guidelines/blob/feature/docs/RC/RC.OnDeviceRankChanged/index.md

[6.2 ActivateApp of SDL Integration Guidelines]: https://app.box.com/s/ohcgjv61cykgkuhycglju6cc4efr0ym3
[6.15 OnExitApplication of SDL Integration Guidelines]: https://app.box.com/s/ohcgjv61cykgkuhycglju6cc4efr0ym3

### Notification

#### Parameters

|Name|Type|Mandatory|Additional|
|:---|:---|:--------|:---------|
|application|[Common.HMIApplication](../../common/structs/#hmiapplication)|true||
|ttsName|[Common.TTSChunk](../../common/structs/#ttschunk)|false|array: true<br>minsize: 1<br>maxsize: 100|
|vrSynonyms|String|false|array: true<br>minsize: 1<br>maxsize: 100<br>maxlength: 40|
|resumeVrGrammars|Boolean|false||
|priority|[Common.AppPriority](../../common/enums/#apppriority)|false||

### Sequence Diagrams
|||
App Register with Resume
![OnAppRegistered](./assets/OnAppRegisteredResume.png)
|||
|||
App Register without Resume
![OnAppRegistered](./assets/OnAppRegisteredNoResume.png)
|||
|||
App Registers on USB
![OnAppRegistered](./assets/OnAppRegisteredUSB.png)
|||
|||
App Registers on Bluetooth
![OnAppRegistered](./assets/OnAppRegisteredBT.png)
|||

Registration of driver's and passenger's RC applications (behavior related to RSDL functionality only).
![OnAppRegistered](./assets/Registration%20of%20driver's%20and%20passenger's%20RC%20applications.png)

#### JSON Example Notification
```json
{
  "jsonrpc" : "2.0",
  "method" : "BasicCommunication.OnAppRegistered",
  "params" :
  {
    "application" :
      {
        "appName" : "TryMe",
        "ngnMediaScreenAppName " : "TryMe",
        "deviceInfo":
                  { "name" : "GT-I9300",
                 "id" : 1563462,
          "transportType" : "BLUETOOTH"
                  },
                  "policyAppID" : 123,
        "appID" : 65540,
        "hmiDisplayLanguageDesired" : ES-ES,
        "isMediaApplication" : false
      }
    "resumeVRGrammars" : true
  }
}
```

#### JSON Example Notification
(related to RSDL functionality only)
```
{
     "jsonrpc" : "2.0",
     "method" : "BasicCommunication.OnAppRegistered",
     “params” :
     {
            "application" : 
            {
                   "appName" : "TryMe",
                   "ngnMediaScreenAppName" : "TryMe",
                   "appType" : "REMOTE_CONTROL",
                   "appID" : 65540,
                   "hmiDisplayLanguageDesired" : "ES-ES",
                   "isMediaApplication" : false ,
                   "policyAppID" : "xyz098"
                   "deviceInfo " : 
                   {
                          "name" : “GT-I9300”,
                          "id" : 1563462,
                          "transportType" : “BLUETOOTH”
                   },
            },
            "vrSynonyms" : "TryMe"
     }
}
```
