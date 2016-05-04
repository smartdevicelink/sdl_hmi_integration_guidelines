## OnAppRegistered


### Notification

#### Parameters

|Name|Type|Mandatory|Additional|Description|
|:---|:---|:--------|:---------|:----------|
|application|Common.HMIApplication|true|||
|ttsName|Common.TTSChunk|false|array: true<br>minsize: 1<br>maxsize: 100||
|vrSynonyms|String|false|array: true<br>minsize: 1<br>maxsize: 100<br>maxlength: 40||
|resumeVrGrammars|Boolean|false|||
|priority|Common.AppPriority|false|||

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

#### TTSChunk

|Name|Type|Mandatory|Additional|Description|
|:---|:---|:--------|:---------|:----------|
|text|String|true|maxlength: 500||
|type|Common.SpeechCapabilities|true|||

#### AppPriority

|Name|Value|
|:---|:----|
|EMERGENCY|0|
|NAVIGATION|1|
|VOICE_COMMUNICATION|2|
|COMMUNICATION|3|
|NORMAL|4|
|NONE|5|

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
