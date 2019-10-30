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

### Example Notification
```json
{
  "jsonrpc" : "2.0",
  "method" : "TTS.Started"
}
```
