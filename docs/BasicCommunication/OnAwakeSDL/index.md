## OnAwakeSDL

Type
: Notification

Sender
: HMI

Purpose
: Notify SDL to return to normal operation after a suspend event.


### Sequence Diagrams
|||
Wake SDL from Suspension
![OnAwakeSDL](./assets/OnAwakeSDL.png)
|||

#### JSON Example Notification
```json
{
  "jsonrpc" : "2.0",
  "method" : "BasicCommunication. OnAwakeSDL"
}
```
