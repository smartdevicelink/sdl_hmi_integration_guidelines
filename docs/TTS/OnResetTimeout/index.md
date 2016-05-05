## OnResetTimeout


### Notification

#### Parameters

|Name|Type|Mandatory|Additional|Description|
|:---|:---|:--------|:---------|:----------|
|appID|Integer|true|||
|methodName|String|true|||

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
