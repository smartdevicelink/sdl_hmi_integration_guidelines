## UpdateAppList


### Request

#### Parameters

|Name|Type|Mandatory|Additional|Description|
|:---|:---|:--------|:---------|:----------|
|applications|Common.HMIApplication|true|array: true<br>minsize: 0<br>maxsize: 100||

#### HMIApplication

|Name|Type|Mandatory|Additional|Description|
|:---|:---|:--------|:---------|:----------|
|appName|String|true|maxlength: 100||
|ngnMediaScreenAppName|String|false|maxlength: 100||
|icon|String|false|||
|deviceInfo|Common.DeviceInfo|true|||
|policyAppID|String|true|minlength: 1<br>maxlength: 50||
|ttsName|Common.TTSChunk|false|array: true<br>minsize: 1<br>maxsize: 100||
|vrSynonyms|String|false|array: true<br>minsize: 1<br>maxsize: 100<br>maxlength: 40||
|appID|Integer|true|||
|hmiDisplayLanguageDesired|Common.Language|false|||
|isMediaApplication|Boolean|false|||
|appType|Common.AppHMIType|false|array: true<br>minsize: 1<br>maxsize: 100||
|greyOut|Boolean|false|||
|requestType|Common.RequestType|false|array: true<br>minsize: 0<br>maxsize: 100||

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
