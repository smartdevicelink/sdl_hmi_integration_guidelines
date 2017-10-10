## GetUserFriendlyMessage

Type
: Function

Sender
: HMI

Purpose
: Get user friendly messages from Policy Table

### Request

!!! MUST
* Request message text to notify user via UI or/and TTS message about some event is happening. Message text may also be requested for some specific dialogs on HMI which require user’s answers.  
* Notify user according to HMI flow via UI pop-ups or/and TTS messages, the text for them obtained in GetUserFriendlyMessage response in correspondence to messageCodes requested.
!!!

!!! NOTE    
_**PoliciesManager must**_ follow to the next steps:   
1. In case HMI respond about supported `<language_1>` via _UI.GetLanguage_response_ to SDL
and HMI sends _SDL.GetUserFriendlyMessage_ request `<language_2>` parameter to SDL and both `<language_1>` and `<language_2>` does NOT exist at "consumer_friendly_messages" section at LocalPT:   
    - retrieve message of en-us sub-section of "consumer_friendly_message" of LocalPT;   
    - provide this message via _SDL.GetUserFriendlyMessage_response_ to HMI.   
2. In case HMI respond about supported `<language_1>` via _UI.GetLanguage_response_ to SDL and HMI sends _SDL.GetUserFriendlyMessage_ request `<language_2>` parameter to SDL and requested `<language_2>` does NOT exist at "consumer_friendly_messages" section at LocalPT
and `<language_1>` exists at "consumer_friendly_messages" section at LocalPT:   
    - retrieve message of `<language_1>` from "consumer_friendly_message" of LocalPT;
    - provide this message via _SDL.GetUserFriendlyMessage_response_ to HMI.   
3. In case HMI sends _SDL.GetUserFriendlyMessage request_ with `<language_1>` parameter and this `<language_1>` exists at "consumer_friendly_message" section of LocalPT:   
    - retrieve message related to requested `<language_1>` from "consumer_friendly_message" section of LocalPT;   
    - provide this message via GetUserFriendlyMessage response to HMI.   
!!!

#### Parameters

|Name|Type|Mandatory|Additional|
|:---|:---|:--------|:---------|
|messageCodes|String|true|array: true<br>minsize: 1<br>maxsize: 100<br>maxlength: 500|
|language|[Common.Language](../../common/enums/#language)|false||

**MessageCodes**   
Message codes specify appropriate user messages which notifies the user about some events/conditions on HMI. Messages and message codes are coming from Policy Table and must be used on HMI in different information pop-ups according to HMI use-cases scenarios.

|MessageCode|MessageText|
|:---|:---------|
|AppPermissions|`appName` is requesting the use of the following vehicle information and permissions `functionalGroupLabels`. Grant requested permission(s)|
|AppPermissionsHelp|`appName` is requesting the following vehicle information and permissions: `functionalGroupLabels`. You can change these permissions and hear detailed descriptions in the mobile apps settings menu. Please press yes to grant permissions or no to deny.|
|AppPermissionsRevoked|App authorizations have changed. `appName` can no longer access `functionalGroupLabels`. Please you have the most recent app version installed on your mobile device.|
|AppUnauthorized|This version of `appName` is not authorized and will not work with Applink. Please update to the latest version of `appName`.|
|AppUnsupported|Your version of `appName` is not supported by SYNC.|
|DataConsent|Would you like to enable Mobile Apps on SYNC? See your Owner Guide for more information.|
|DataConsentHelp|Updates are about the size of an email, and the occurrence of updates depends on your vehicle usage and when a new app is found on your device. See your Owner Guide for more information.|
|DisableApps|Disabling automatic updates will also disable sync mobile apps. You will not be able to use any mobile apps with SYNC. Please press yes to confirm or no to cancel.|
|DrivingCharacteristics|An app can access the following driving characteristics: Fuel Consumption, MyKey, Seat Belt Status.|
|Location|An app can access vehicle GPS and speed.|
|Notifications|An app can send notifications when running in the background.|
|SettingDisableUpdates|Disable Updates|
|SettingEnableUpdates|Enable Apps|
|SettingUpdateAuto|Select `Update now` to receive app authorization information for your SYNC-enabled mobile apps. This may enable additional functionality depending on the app and your settings. If your phone has a working data connection, an update should complete in less than 1 minute.|
|StatusNeeded|Update Needed|
|StatusPending|Updating...|
|StatusUpToDate|Up-To-Date|
|VehicleInfo|An app can access the following vehicle information: Fuel Level, Fuel Economy, Engine RPMs, Odometer, VIN, External Temperature, Gear Position, Tire Pressure.|

!!! NOTE
“MessageText” column specifies the messages just for an information purposes. The MessageText received from SDL may differ from listed in the table.
!!!

### Response

#### Parameters

|Name|Type|Mandatory|Additional|
|:---|:---|:--------|:---------|
|messages|[Common.UserFriendlyMessage]|false|array: true<br>minsize: 1<br>maxsize: 100|
[Common.UserFriendlyMessage]: ../../common/structs/#userfriendlymessage

### Sequence Diagrams
|||
GetUserFriendlyMessage for device consent
![GetUserFriendlyMessage](./assets/GetUserFriendlyMessage.png)
|||

### Example Request

```json
{
  "id" : 176,
  "jsonrpc" : "2.0",
  "method" : "SDL.GetUserFriendlyMessage",
  "params" :
  {
    "messageCodes": "AppPermissions",    
      "language" : "EN-GB"
  }

}
```
### Example Response

```json
{
  "id" : 176,
  "jsonrpc" : "2.0",
  "result" :
  {
    "messages": {
             "messageCode": "AppPermissions",
             "ttsString": "%appName% is requesting the use of the following ....",
             line1: "Grant Requested",
             line2: "Permission(s)?"
            },
    "code" : 0,
    "method" : "SDL.GetUserFriendlyMessage"
  }
}
```

### Example Error

```json
{
  "id" : 176,
  "jsonrpc" : "2.0",
  "error" :
  {
    "code" :22,
    "message" : "Some error occurred",
    "data" :
    {
      "SDL.GetUserFriendlyMessage"
    }
  }
}
```
