## OnAppPermissionChanged

Type
: Notification

Sender
: SDL

Purpose
: Inform HMI that permissions have changed for a specified application.

### Notification

#### Parameters

|Name|Type|Mandatory|Additional|
|:---|:---|:--------|:---------|
|appID|Integer|true||
|isAppPermissionsRevoked|Boolean|false||
|appRevokedPermissions|[Common.PermissionItem](../../Common/Structs/index.md#permissionitem)|false|array: true<br>minsize: 1<br>maxsize: 100|
|appRevoked|Boolean|false||
|appPermissionsConsentNeeded|Boolean|false||
|appUnauthorized|Boolean|false||
|priority|[Common.AppPriority](../../Common/Enums/index.md#apppriority)|false||
|requestType|[Common.RequestType](../../Common/Enums/index.md#requesttype)|false|array: true<br>minsize: 0<br>maxsize: 100|

### Sequence Diagrams
|||
OnAppPermissionChanged with consent required
![OnAppPermissionChanged](./assets/OnAppPermissionChanged.png)
|||

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
