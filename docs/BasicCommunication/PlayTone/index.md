## PlayTone


### Notification

#### Parameters

|Name|Type|Mandatory|Additional|Description|
|:---|:---|:--------|:---------|:----------|
|appID|Integer|true|||
|methodName|Common.MethodName|true|||

#### MethodName

|Name|Value|
|:---|:----|
|ALERT|0|
|SPEAK|1|
|AUDIO_PASS_THRU|2|
|ALERT_MANEUVER|3|

### Sequence Diagrams
|||
Play Tone with Alert
![PlayTone](./assets/PlayTone.png)
|||

### Example Request

```json
{
	"jsonrpc" : "2.0",
	"method" : "BasicCommunication.PlayTone",
"params" :
	{
		"appID" : 123,
      "methodName": "ALERT"
	}

}
```
### Example Response

```json
{
	"id" : 47,
	"jsonrpc" : "2.0",
	"result" :
	{
		"code" : 0,
		"method" : "BasicCommunication. PlayTone"
	}
}
```

### Example Error

```json
{
	"id" : 47,
	"jsonrpc" : "2.0",
	"error" :
	{
		"code" : 22,
		"message" : " Unknown system error",
		"method" : "BasicCommunication.PlayTone"
	}
}
```
