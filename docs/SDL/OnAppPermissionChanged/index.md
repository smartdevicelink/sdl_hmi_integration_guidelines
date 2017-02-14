## OnAppPermissionChanged

Type
: Notification

Sender
: SDL

Purpose
: Inform HMI that permissions have changed for a specified application.

Notification from SDL to HMI occurs when application permissions were changed. If no permission specified means that application was dissallowed and has to be unregistered.

**HMI must:**  
1.  Request the list of permissions per app for which the consent is required (via `GetListOfPermissions`) when HMI gets the 'user-consent-required' notification per app from `SDL (SDL.OnAppPermissionChanged{appID, appPermissionsConsentNeeded: true})`.  
2.  Request Policies Manager for the appropriate user-friendly message from Local PT (`SDL.GetUserFriendlyMessage`) to commuticate about permissions changed when HMI gets the list of permissions that require User's consent.

_It is app’s responsibility to inform the user to change the app’s settings if user consent is needed for proper app operation.  
Any permissions that require user consent are not enabled until a user accepts them. If permissions do not require user consent, they can be applied immediately._ 

_SDL Note:_  
1. SDL sends the list of RequestTypes allowed by Policies via `OnAppPermissionChanged` API. In case HMI will use any of requestTypes disallowed by PolicyTable, SDL will ignore such notifications.  
2. SDL PoliciesManager must send `OnAppPermissionChanged (appRevoked: true, appID)`and `BC.ActivateApp` (NONE) to HMI, in case the  `<appID>`  application is currently registered and in any HMILevel and in result of PTU  `<appID>`  gets "null" policies.   
3. If app permissions were reduced after PTU, SDL sends `OnAppPermissionChanged (isAppPermissionsRevoked: true)` when app is in FULL or LIMITTED. SDL doesn't notify HMI about revoked permissions twice.  
4. In case the Local PT is successfully updated AND there are new application permissions that require User's consent, Policies Manager must:  
a) notify HMI about 'user-consent-required' via `SDL.OnAppPermissionChanged{appID, appPermissionsConsentNeeded: true}` per each application in FULL/LIMITED that lacks the User's permissions right after Policies Manager detects the user-unconsented permissions in Local PT  
b) notify HMI about 'user-consent-required' `SDL.OnAppPermissionChanged{appID, appPermissionsConsentNeeded: true} after the related app is activated on HMI (in case the related app is now in BACKGROUND /NONE HMILevel)`.  
5. In case the Local PT is successfully updated AND there are new permissions that require User's consent, Policies Manager must:  
  a) notify HMI about 'user-consent-required' via `SDL.OnAppPermissionChanged{appID, appPermissionsConsentNeeded: true}` per each application that lacks the User's permissions  
  b) provide the list of permissions that require User's consent upon request from HMI via `GetListOfPermissions(appID)`
 
### Notification

#### Parameters

|Name|Type|Mandatory|Additional|
|:---|:---|:--------|:---------|
|appID|Integer|true||
|isAppPermissionsRevoked|Boolean|false||
|appRevokedPermissions|[Common.PermissionItem](https://github.com/smartdevicelink/sdl_hmi_integration_guidelines/blob/master/docs/Common/Structs/index.md#permissionitem)|false|array: true<br>minsize: 1<br>maxsize: 100|
|appRevoked|Boolean|false||
|appPermissionsConsentNeeded|Boolean|false||
|appUnauthorized|Boolean|false||
|priority|[Common.AppPriority](https://github.com/smartdevicelink/sdl_hmi_integration_guidelines/blob/master/docs/Common/Enums/index.md#apppriority)|false||
|requestType|[Common.RequestType](https://github.com/smartdevicelink/sdl_hmi_integration_guidelines/blob/master/docs/Common/Enums/index.md#requesttype)|false|array: true<br>minsize: 0<br>maxsize: 100|

### Sequence Diagrams

OnAppPermissionChanged with consent required
![OnAppPermissionChanged](./assets/OnAppPermissionChanged.png)


#### JSON Example Notification
```json
{
  "jsonrpc" : "2.0",
  "method" : "SDL.OnAppPermissionChanged",
  "params" :  
  {
    "appID" : 65674,

  }
}
```
