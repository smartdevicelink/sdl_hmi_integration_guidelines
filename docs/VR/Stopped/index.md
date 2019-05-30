## Stopped

Type
: Notification

Sender
: HMI

Purpose
: Inform SDL about the end of a VR session.

### Notification

### Sequence Diagrams
|||
Stopped when VR session ends
![Stopped](./assets/Stopped.png)
|||

### Example Notification

```json
{
  "jsonrpc" : "2.0",
  "method" : "VR.Stopped"
}
```
