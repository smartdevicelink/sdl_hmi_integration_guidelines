## StopSpeaking

Type
: Function

Sender
: SDL

Purpose
: Interrupt the current spoken session.

### Request

#### Parameters

|Name|Type|Mandatory|Additional|Description|
|:---|:---|:--------|:---------|:----------|

### Response

#### Parameters

This RPC has no additional parameter requirements

### Sequence Diagrams
|||
StopSpeaking
![StopSpeaking](./assets/StopSpeaking.png)
|||

### Example Request

```json
{
	"id" : 148,
	"jsonrpc" : "2.0",
	"method" : "TTS.StopSpeaking"
}
```
### Example Response

```json
{
	"id" : 148,
	"jsonrpc" : "2.0",
	"result" :
	{
		"code" : 0,
		"method" : "TTS.StopSpeaking"
	}
}
```

### Example Error

```json
{
	"id" : 148,
	"jsonrpc" : "2.0",
	"error" :
	{
		"code" : 11,
		"message" : "Invalid data: invalid JSON syntax",
		"data" :
		{
			"method" : "TTS.StopSpeaking"
		}
	}
}
```
