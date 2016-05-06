## ChangeRegistration

Type
: Function

Sender
: SDL

Purpose
: Change the language of the TTS component.

### Request

#### Parameters

|Name|Type|Mandatory|Additional|
|:---|:---|:--------|:---------|
|ttsName|[Common.TTSChunk](../../Common/Structs/index.md#ttschunk)|false|array: true<br>minsize: 1<br>maxsize: 100|
|language|[Common.Language](../../Common/Enums/index.md#language)|true||
|appID|Integer|true||

### Response

#### Parameters

This RPC has no additional parameter requirements

### Sequence Diagrams
|||
ChangeRegistration after OnAppRegistered
![ChangeRegistration](./assets/ChangeRegistration.png)
|||

### Example Request

```json
{
	"id" : 206,
	"jsonrpc" : "2.0",
	"method" : "TTS.ChangeRegistration",
	"params" :
	{
		"language" : DE-DE,
		"appID" : 65539
	}
}
```
### Example Response

```json
{
	"id" : 206,
	"jsonrpc" : "2.0",
	"result" :
	{
		"code" : 0,
		"method" : "TTS.ChangeRegistration"
	}
}
```

### Example Error

```json
{
	"id" : 206,
	"jsonrpc" : "2.0",
	"error" :
	{
		"code" : 22,
		"message" : "Unknown error occurred",
		"data" :
		{
			"method" : "TTS.ChangeRegistration"
		}
	}
}
```
