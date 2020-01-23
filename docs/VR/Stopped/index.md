## Stopped

Type
: Notification

Sender
: HMI

Purpose
: Inform SDL about the end of a VR session.

### Notification

#### Parameters

This RPC has no additional parameter requirements

### Sequence Diagrams

|||
Stopped when VR session ends
![Stopped](./assets/Stopped.png)
|||

### JSON Message Examples

#### Example Notification

```json
{
  "jsonrpc" : "2.0",
  "method" : "VR.Stopped"
}
```
