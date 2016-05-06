## Speak

Type
: Function

Sender
: SDL

Purpose
: Prompt TTS to speak the requested text to the user.

### Request

#### Parameters

|Name|Type|Mandatory|Additional|
|:---|:---|:--------|:---------|
|ttsChunks|[Common.TTSChunk](../../Common/Structs/index.md#ttschunk)|true|array: true<br>minsize: 1<br>maxsize: 100|
|appID|Integer|true||
|speakType|[Common.MethodName](../../Common/Enums/index.md#methodname)|false||

### Response

#### Parameters

|Name|Type|Mandatory|Additional|
|:---|:---|:--------|:---------|

### Sequence Diagrams
|||
Speak
![Speak](./assets/Speak.png)
|||

### Example Request

```json
{
	"id" : 144,
	"jsonrpc" : "2.0",
	"method" : "TTS.Speak",
	"params" :
	{
		"ttsChunks" :
		[
			"text" : "Please say a command"
		]
	}
}
```
### Example Response

```json
{
	"id" : 144,
	"jsonrpc" : "2.0",
	"result" :
	{
		"code" : 0,
		"method" : "TTS.Speak"
	}
}
```

### Example Error

```json
{
	"id" : 144,
	"jsonrpc" : "2.0",
	"error" :
	{
		"code" : 5,
		"message" : "The command was aborted",
		"data" :
		{
			"method" : "TTS.Speak"
		}
	}
}
```
