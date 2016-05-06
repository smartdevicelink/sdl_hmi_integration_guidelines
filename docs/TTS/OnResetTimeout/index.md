## OnResetTimeout

Type
: Notification

Sender
: HMI

Purpose
: Inform SDL to reset the timeout if speaking is running over the default timeout.

### Notification

#### Parameters

|Name|Type|Mandatory|Additional|
|:---|:---|:--------|:---------|
|appID|Integer|true||
|methodName|String|true||

### Sequence Diagrams
|||
OnResetTimeout for Speak SUCCESS
![OnResetTimeout](./assets/OnResetTimeoutSpeakSuccess.jpg)
|||
|||
OnResetTimeout for Speak GENERIC_ERROR
![OnResetTimeout](./assets/OnResetTimeoutGenericError.jpg)
|||

#### JSON Example Notification
```json
{
	"jsonrpc" : "2.0",
	"method" : "TTS.OnResetTimeout",
     "params" :
	{
		"appID" : 123,
		"methodName" : "Speak"

	}
}
```
