## Started

Type
: Notification

Sender
: HMI

Purpose
: Inform SDL that TTS has started.

### Notification

#### Parameters

This RPC has no additional parameter requirements.

### Sequence Diagrams
|||
Started upon TTS.Speak request from SDL
![Started](./assets/StartedFromSpeak.png)
|||
|||
Started during PerformInteraction
![Started](./assets/StartedFromPerformInteraction.png)
|||

### Example Request

```json
{
  "jsonrpc" : "2.0",
  "method" : "TTS.Started"
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
    "method" : "TTS.Started"
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
    "code" : 22,
    "message" : "Something went wrong",
    "data" :
    {
      "method" : "TTS.Started"
    }
  }
}
```
