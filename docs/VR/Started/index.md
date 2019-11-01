## Started

Type
: Notification

Sender
: HMI

Purpose
: Inform SDL about the start of a VR session

### Notification

#### Parameters

This RPC has no additional parameter requirements

### Sequence Diagrams
|||
Started on PTT Button Press
![Started](./assets/Started.png)
|||

### JSON Message Examples

#### Example Notification

```json
{
  "jsonrpc" : "2.0",
  "method" : "VR.Started"
}
```

