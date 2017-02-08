## OnAppPermissionChanged

Type
: Notification

Sender
: SDL

Purpose
: Inform HMI that permissions have changed for a specified application.

Notification from SDL to HMI occurs when application permissions were changed. If no permission specified means that application was dissallowed and has to be unregistered.

_**Note:**_    

   - SDL sends the list of RequestTypes allowed by Policies via _OnAppPermissionChanged_ API. In case HMI will use some not allowed by PolicyTable, SDL will ignore all notifications from HMI which contain prohibited RequestTypes values (e.g. sent via _OnSystemRequest_).
   - SDL PoliciesManager must send _OnAppPermissionChanged_ (appRevoked: true, appID) and BC.ActivateApp (NONE) to HMI, in case the `<appID>` application is currently registered and in any HMILevel and in result of PTU `<appID>` gets "null" policies. 

### Notification

#### Parameters

|Name|Type|Mandatory|Additional|
|:---|:---|:--------|:---------|
|appID|Integer|true||
|isAppPermissionsRevoked|Boolean|false||
|appRevokedPermissions|[Common.PermissionItem]|false|array: true<br>minsize: 1<br>maxsize: 100|
|appRevoked|Boolean|false||
|appPermissionsConsentNeeded|Boolean|false||
|appUnauthorized|Boolean|false||
|priority|[Common.AppPriority]|false||
|requestType|[Common.RequestType]|false|array: true<br>minsize: 0<br>maxsize: 100|

[Common.PermissionItem]: https://github.com/smartdevicelink/sdl_hmi_integration_guidelines/blob/develop/docs/Common/Structs/index.md#permissionitem
[Common.AppPriority]: https://github.com/smartdevicelink/sdl_hmi_integration_guidelines/blob/develop/docs/Common/Enums/index.md#apppriority
[Common.RequestType]: https://github.com/smartdevicelink/sdl_hmi_integration_guidelines/blob/develop/docs/Common/Enums/index.md#requesttype


### Sequence Diagrams
_**Pre-conditions to the sequence:**_   
a) SDL and HMI are started;   
b) Device is connected to the System (SDL/HU) and is consented by the User;   
c) Four apps are registered with SDL and HMI ('name_HMILevel'): app_FULL, app_LIMITED, app_BACKGROUND, app_NONE.

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
