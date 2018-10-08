## SetGlobalProperties

Type
: Function

Sender
: SDL

Purpose
: Set the properties for the TTS component.

### Request

#### Parameters

|Name|Type|Mandatory|Additional|
|:---|:---|:--------|:---------|
|helpPrompt|[Common.TTSChunk](../../common/structs/#ttschunk)|false|array: true<br>minsize: 0<br>maxsize: 100|
|timeoutPrompt|[Common.TTSChunk](../../common/structs/#ttschunk)|false|array: true<br>minsize: 1<br>maxsize: 100|
|appID|Integer|true||

### Response

#### Parameters

This RPC has no additional parameter requirements

### Sequence Diagrams
|||
SetGlobalProperties
![SetGlobalProperties](./assets/SetGlobalProperties.png)
|||

### Example Request

```json
{
  "id" : 37,
  "jsonrpc" : "2.0",
  "method" : "TTS.SetGlobalProperties",
  "params" :
  {
    "helpPrompt" :
    [
      {
        "text" : "Yes", 
        "type" : "TEXT"
      },
      {
        "text" : "No", 
        "type" : "TEXT"
      },
      {
        "text" : "Skip", 
        "type" : "TEXT"
      }
    ],

    "timeoutPrompt" :
    [
      {
        "text" : "Please make a choice", 
        "type" : "TEXT"
      },
      {
        "text" : "The time is about to expire", 
        "type" : "TEXT"
      }
    ],
    "appID" : 65542
  }
}
```
### Example Response

```json
{
  "id" : 37,
  "jsonrpc" : "2.0",
  "result" :
  {
    "code" : 0,
    "method" : "TTS.SetGlobalProperties"
  }
}
```

### Example Error

```json
{
  "id" : 37,
  "jsonrpc" : "2.0",
  "error" :
  {
    "code" : 2,
    "message" : "TTS is not supported",
    "data" :
    {
      "method" : "TTS.SetGlobalProperties"
    }
  }
}
```
