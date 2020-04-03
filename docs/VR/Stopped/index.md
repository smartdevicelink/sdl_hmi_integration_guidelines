## Stopped

Type
: Notification

Sender
: HMI

Purpose
: Inform SDL about the end of a <span title="Voice Recognition">VR</span> session.

### Notification

#### Parameters

This RPC has no additional parameter requirements

### Sequence Diagrams

|||
Stopped when <span title="Voice Recognition">VR</span> session ends
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
