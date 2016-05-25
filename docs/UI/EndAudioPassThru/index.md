## EndAudioPassThru

Type
: Function

Sender
: SDL

Purpose
: Stop audio capturing and sending PCM data to SDL

### Request

#### Parameters

|Name|Type|Mandatory|Additional|
|:---|:---|:--------|:---------|

### Response

#### Parameters

This RPC has no additional parameter requirements

### Sequence Diagrams
|||
EndAudioPassThru stops audio capturing
![EndAudioPassThru](./assets/EndAudioPassThru.png)
|||
|||
EndAudioPassThru audio capturing already ended
![EndAudioPassThru](./assets/EndAudioPassThruTooLate.png)
|||

### Example Request

```json
{
  "id" : 79,
  "jsonrpc" : "2.0",
  "method" : "UI.EndAudioPassThru",
}
```
### Example Response

```json
{
  "id" : 79,
  "jsonrpc" : "2.0",
  "result" :
  {
    "code" : 0,
    "method" : "UI.EndAudioPassThru"
  }
}
```

### Example Error

```json
{
  "id" : 79,
  "jsonrpc" : "2.0",
  "error" :
  {
    "code" : 4,
    "message" : "Rejected: no PerformAudioPassThru is now active",
    "data" :
    {
      "method" : "UI.EndAudioPassThru"
    }
  }
}
```
