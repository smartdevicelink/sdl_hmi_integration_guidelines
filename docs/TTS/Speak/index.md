## Speak

Type
: Function

Sender
: SDL

Purpose
: Prompt TTS to speak the requested text to the user.

### Request

In case HMI needs more time for processing TTS.Speak request, HMI must send BC.OnResetTimeout notification to SDL for reseting timeout.

_SDL Note: In case HMI does not respond SDL's request during timeout, SDL will return GENERIC_ERROR code to the corresponding mobile app's request._

#### Parameters

|Name|Type|Mandatory|Additional|
|:---|:---|:--------|:---------|
|ttsChunks|[Common.TTSChunk](../../common/structs/#ttschunk)|true|array: true<br>minsize: 1<br>maxsize: 100|
|appID|Integer|true||
|speakType|[Common.MethodName](../../common/enums/#methodname)|false||
|playTone|Boolean|false||

### Response

#### Parameters

This RPC has no additional parameter requirements.

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
      {
        "text" : "Please say a command", 
        "type" : "TEXT"
      }
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
