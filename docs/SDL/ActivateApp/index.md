## ActivateApp

Type
: Function

Sender
: HMI

Purpose
: Inform SDL that the user has activated an application.

### Request

#### Parameters

|Name|Type|Mandatory|Additional|
|:---|:---|:--------|:---------|
|appID|Integer|true||

### Response

#### Parameters

|Name|Type|Mandatory|Additional|
|:---|:---|:--------|:---------|
|isSDLAllowed|Boolean|true||
|device|[Common.DeviceInfo](../../Common/Structs/index.md#deviceinfo)|false||
|isPermissionsConsentNeeded|Boolean|true||
|isAppPermissionsRevoked|Boolean|true||
|appRevokedPermissions|[Common.PermissionItem](../../Common/Structs/index.md#permissionitem)|false|array: true<br>minsize: 1<br>maxsize: 100|
|isAppRevoked|Boolean|true||
|priority|[Common.AppPriority](../../Common/Enums/index.md#apppriority)|false||

### Sequence Diagrams
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
