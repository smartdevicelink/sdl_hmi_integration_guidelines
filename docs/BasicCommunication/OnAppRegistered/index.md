## OnAppRegistered

Type
: Notification

Sender
: SDL

Purpose
: Update the HMI's list of registered applications and resume the Audio Source

### Notification

#### Parameters

|Name|Type|Mandatory|Additional|
|:---|:---|:--------|:---------|
|application|[Common.HMIApplication](../../Common/Structs/index.md#hmiapplication)|true||
|ttsName|[Common.TTSChunk](../../Common/Structs/index.md#ttschunk)|false|array: true<br>minsize: 1<br>maxsize: 100|
|vrSynonyms|String|false|array: true<br>minsize: 1<br>maxsize: 100<br>maxlength: 40|
|resumeVrGrammars|Boolean|false||
|priority|[Common.AppPriority](../../Common/Enums/index.md#apppriority)|false||

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
