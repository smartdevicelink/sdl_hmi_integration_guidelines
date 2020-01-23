## OnAwakeSDL

Type
: Notification

Sender
: HMI

Purpose
: Notify SDL to return to normal operation after a suspend event.

This notification is sent to SDL to notify that there won't be `IGNITION_OFF` sent after [OnExitAllApplications](../onexitallapplications)(`SUSPEND`), which was previously sent by the HMI.

!!! MAY

  1. Send `OnAwakeSDL` if the `ACC` does not change, but the driver door is opened and closed two times.
  2. Send `OnAwakeSDL` if the `ACC` key position is set to `On`.

!!!

### Notification

#### Parameters

This RPC has no additional parameter requirements

### Sequence Diagrams

|||
Wake SDL from Suspension
![OnAwakeSDL](./assets/OnAwakeSDL.png)
|||

### JSON Message Examples

#### Example Notification

```json
{
  "jsonrpc" : "2.0",
  "method" : "BasicCommunication.OnAwakeSDL"
}
```
