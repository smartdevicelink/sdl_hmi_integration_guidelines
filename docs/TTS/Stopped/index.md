## Stopped

Type
: Notification

Sender
: HMI

Purpose
: Inform SDL that TTS has stopped.

### Notification

#### Parameters

This RPC has no additional parameter requirements.

### Sequence Diagrams
|||
Stopped after StopSpeaking from SDL
![Stopped](./assets/Stopped.png)
|||

### JSON Example Notification
```json
{
  "jsonrpc" : "2.0",
  "method" : "TTS.Stopped"
}
```