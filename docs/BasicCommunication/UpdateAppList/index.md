## UpdateAppList

Type
: Function

Sender
: SDL

Purpose
: Update HMI's list of registered applications.


### Request

#### Parameters

|Name|Type|Mandatory|Additional|
|:---|:---|:--------|:---------|
|applications|[Common.HMIApplication](../../Common/Structs/index.md#hmiapplication)|true|array: true<br>minsize: 0<br>maxsize: 100|

### Response

#### Parameters

This RPC has no additional parameter requirements

### Sequence Diagrams
|||
Application Just Registered
![UpdateAppList](./assets/UpdateAppListAppRegister.png)
|||
|||
User Requests Update App List
![UpdateAppList](./assets/UpdateAppListUser.png)
|||

### Example Request

```json
{
	"id" : 75,
	"jsonrpc" : "2.0",
	"method" : "BasicCommunication.UpdateAppList",
	"params" :
	{
		"applications" :
		[
			{
				"appName" : "Beautiful Sound",
				"ngnMediaScreenAppName " : "BeauSo",
				"deviceName" : "Jerry`s Phone",
				"appID" : 65544,
				"hmiDisplayLanguageDesired" : "DE-DE",
				"isMediaApplication" : true
			},

			{
				"appName" : "Go Travel",
				"icon" : "tmp/SDL/app/Go_Travel/icon.png",
				"deviceName" : "XT910",
				"appID" : 65545,
				"hmiDisplayLanguageDesired" : "EN-US",
				"isMediaApplication" : false,
        "appType" : "INFORMATION"
			}
		]
	}
}
```
### Example Response

```json
{
	"id" : 75,
	"jsonrpc" : "2.0",
	"result" :
	{
		"code" : 0,
		"method" : "BasicCommunication.UpdateAppList"
	}
}
```

### Example Error

```json
{
	"id" : 75,
	"jsonrpc" : "2.0",
	"error" :
	{
		"code" : 22,
		"message" : "During the API call an unknown error has occurred.",
		"data" :
		{
			"method" : "BasicCommunication.UpdateAppList"
		}
	}
}
```
