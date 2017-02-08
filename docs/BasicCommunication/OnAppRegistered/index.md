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

Data resumption means that an application may request to restore data used in the previous ignition cycle after an `Unexpected Disconnect`.


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

If the application does NOT resume data successfully:

  * SDL will provide `OnAppRegistered` with `resumeVrGrammars`:`false` or no resume parameter at all.
  * SDL cleans up all previously stored application data for the application that failed to resume. The HMI must also clean up previously compiled `VRGrammars` for the application.
  * The application will send new data to start SDL operations. In this event, SDL and the HMI should restart the cycle of collecting application data for resumption.

_**HMI must:**_

  1. Update its list of registered applications.
  2. Store the application data sent in the `applications` parameter.
  3. Compile and store `VRGrammars` for the `vrSynonyms` parameter, and arrange them for the user to be able to use via voice recognition. Note: The VR commands to activate an application must be accessible when viewing a different active application or the list of registered applications.
  4. Provide the user with the possibility to choose an application among a list of registered applications.
  5. Send an `OnAppActivated` notification to SDL when the user activates an app via the `UI` or `VR`.   
  6. Manage application events by priority. HMI gets proirity information from _OnAppRegistered_, _UpdateAppList_, _ActivateApp_ HMI API.

_**Note:**_   

   - If a device is connected over USB and registers an application, SDL will send `OnAppRegistered` with a hash of the usb serial number as the device id.
   - If a device is connected over Bluetooth or Wi-Fi and registers an application, SDL will send `OnAppRegistered` with a hash of the device's mac address as the device id.
   - When the application is registered for the first time (no records in PT) PoliciesManager should not initiate prompting the User about the event.


### Notification

#### Parameters

|Name|Type|Mandatory|Additional|
|:---|:---|:--------|:---------|
|application|[Common.HMIApplication]|true||
|ttsName|[Common.TTSChunk]|false|array: true<br>minsize: 1<br>maxsize: 100|
|vrSynonyms|String|false|array: true<br>minsize: 1<br>maxsize: 100<br>maxlength: 40|
|resumeVrGrammars|Boolean|false||
|priority|[Common.AppPriority]|false||

[Common.HMIApplication]: https://github.com/smartdevicelink/sdl_hmi_integration_guidelines/blob/develop/docs/Common/Structs/index.md#hmiapplication
[Common.TTSChunk]: https://github.com/smartdevicelink/sdl_hmi_integration_guidelines/blob/develop/docs/Common/Structs/index.md#ttschunk
[Common.AppPriority]: https://github.com/smartdevicelink/sdl_hmi_integration_guidelines/blob/develop/docs/Common/Enums/index.md#apppriority

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
