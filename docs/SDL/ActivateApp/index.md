## ActivateApp

Type
: Function

Sender
: HMI

Purpose
: Inform SDL that the user has activated an application.

### Request

!!! MUST   

1. Follow to steps:  
   - send _GetListOfPermissions_ request to SDL (if "isPermissionsConsentNeeded:true" is set to true) in order to obtain list of message codes for functional groups needed by application for user to consent, in response SDL provides array of these message codes.    
   - send _GetUserFriendlyMessage_ request to SDL to obtain user friendly messages from policy table with list of message codes and optionally language if language needs to be different from provided by HMI on startup (using GetLanguage request from SDL).   
!!! NOTE
   In response SDL sends messages from policy table. 
   - display appropriate dialog to User and sends _OnAppPermissionConsent_ notification to SDL specifying _app_id_, consented functions and source.
!!!

2. Display Dialog and on result of user selection to send _OnAllowSDLFuncionality_ specifying device from _ActivateApp_ response, source of choice (UI/VR) and allowed set to true/false (if user ignores question, this is automatically set to false), in case HMI receives _SDL.ActivateApp_ (isSDLAllowed: false).
!!!

!!! NOTE   
_**SDL PoliciesManager must**_:
   - respond with "isPermissionsConsentNeeded: true", otherwise "isPermissionsConsentNeeded: false" should be returned to HMI, in case SDL got _SDL.ActivateApp_ from HMI and LocalPT contains the permission that require User\`s consent.
   - respond with "isSDLAllowed: true" in the response to HMI, on getting _SDL.ActivateApp_ from HMI and the device the app is running on is consented by the User.   
   - respond with the following parameters in the response to HMI:   
        - "isSDLAllowed: false";   
        - _device_ param containing the device\`s name and ID previously sent by SDL via _UpdateDeviceList_.
!!!

#### Parameters

|Name|Type|Mandatory|Description|
|:---|:---|:--------|:----------|
|appID|Integer|true|ID of the application that the User has chosen.|

### Response

#### Parameters

|Name|Type|Mandatory|Description|
|:---|:---|:--------|:----------|
|isSDLAllowed|Boolean|true|SDL returns:‘true’, in case the User has allowed using the device for PolicyTable Exchange. ‘false’, in case the User has not yet been asked for or in case the User has disallowed using the device for PolicyTable Exchange.|
|device|[Common.DeviceInfo]|false||
|isPermissionsConsentNeeded|Boolean|true||
|isAppPermissionsRevoked|Boolean|true||
|appRevokedPermissions|[Common.PermissionItem]|false|array: true<br>minsize: 1<br>maxsize: 100|
|isAppRevoked|Boolean|true||
|priority|[Common.AppPriority]|false||

[Common.DeviceInfo]: ../../common/structs/#deviceinfo

[Common.PermissionItem]: ../../common/structs/#permissionitem

[Common.AppPriority]: ../../common/enums/#apppriority

### Sequence Diagrams

Preconditions:   
a) Device is connected to the HU.   
b) App_1 is running on this device and is registered with SDL.   
c) App_1 presents in the list of registered apps on HMI.

|||
1. The User does NOT consent the device.
![ActivateApp](./assets/User%20does%20not%20consent%20the%20device1.png)
|||

|||
2. The User consents the device.
![ActivateApp](./assets/User%20consents%20the%20device2.png)
|||

|||
ActivateApp for application registered with reduced permissions after Policy Table Update
![ActivateApp](./assets/ActivateAppReducedPermissions.png)
|||
|||
ActivateApp for application registered with revoked permissions after Policy Table Update
![ActivateApp](./assets/ActivateAppRevokedPermissions.png)
|||
|||
ActivateApp using App Launching
![ActivateApp](./assets/ActivateAppAppLaunch.png)
|||

### Example Request

```json
{
  "id" : 27,
  "jsonrpc" : "2.0",
  "method" : "SDL.ActivateApp"
  "params" :
  {
    "appID" : 12345
  }
}
```
### Example Response

```json
{
  "id" : 27,
  "jsonrpc" : "2.0",
  "result" :
  {
    "isSDLAllowed" : true,
    "isPermissionsConsentNeeded" : false,
    "isAppPermissionsRevoked" : false,
    "isAppRevoked" : false,
    "code" : 0,
    "method" : "SDL.ActivateApp"
  }
}
```

### Example Error

```json
{
  "id" : 27,
  "jsonrpc" : "2.0",
  "error" :
  {
    "code" : 22,
    "message" : "The unknown error has occurred",
    "data" :
    {
      "method" : "SDL.ActivateApp"
    }
  }
}
```
