## AddCommand

Type
: Function

Sender
: SDL

Purpose
: Add a command to the specified application's menu or sub menu

### Request

#### Parameters

|Name|Type|Mandatory|Additional|
|:---|:---|:--------|:---------|
|cmdID|Integer|true|minvalue: 0<br>maxvalue: 2000000000|
|menuParams|[Common.MenuParams](../../Common/Structs/index.md#menuparams)|false||
|cmdIcon|[Common.Image](../../Common/Structs/index.md#image)|false||
|appID|Integer|true||

### Response

#### Parameters

This RPC has no additional parameter requirements

### Sequence Diagrams
|||
AddCommand Command Chosen By User
![AddCommand](./assets/AddCommandChosen.png)
|||
|||
AddCommand App Inactive
![AddCommand](./assets/AddCommandAppInactive.png)
|||
|||
AddCommand with sub menu
![AddCommand](./assets/AddCommandSubMenu.png)
|||
|||
AddCommand positions
![AddCommand](./assets/AddCommandPositions.png)
|||
|||
AddCommand Rejected Limit Reached
![AddCommand](./assets/AddCommandRejectedLimit.png)
|||
|||
AddCommand UI Succeeds, VR Fails
![AddCommand](./assets/AddCommandVRFail.png)
|||
|||
AddCommand UI Succeeds, VR Unresponsive
![AddCommand](./assets/AddCommandVRNoResponse.png)
|||
|||
AddCommand UI Fails, VR Succeeds
![AddCommand](./assets/AddCommandFailVRSuccess.png)
|||
|||
AddCommand UI No Response, VR Succeeds
![AddCommand](./assets/AddCommandUINoResponseVRSuccess.png)
|||

### Example Request

```json
{
	"id" : 215,
	"jsonrpc" : "2.0",
	"method" : "UI. AddCommand",
	"params" :
	{
		"cmdID" : 2318,
		"menuParams" :
		 {
				 "parentID" : 6,
				 "position" : 0,
				 "menuName" : "Show weather for tomorrow"
		 },
		"cmdIcon" :
		 {
				 "value" : "tmp/SDL/app/Gis_meteo/1245_28.jpeg",
				 "imageType" : DYNAMIC
		 },
		"appID" : 65409
	}
}
```
### Example Response

```json
{
	"id" : 215,
	"jsonrpc" : "2.0",
	"result" :
	{
		"code" : 0,
		"method" : "UI.AddCommand"
	}
}
```

### Example Error

```json
{
	"id" : 215,
	"jsonrpc" : "2.0",
	"error" :
	{
		"code" : 13,
		"message" : "There’s no app with received appID registered",
		"data" :
		{
			"method" : "UI.AddCommand"
		}
	}
}
```
