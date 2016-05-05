## OnSDLPersistenceComplete

Type
: Notification

Sender
: SDL

Purpose
: Inform HMI that any data persistence operations have been completed.


### Notification

#### Parameters

This RPC has no additional parameter requirements

### Sequence Diagrams
|||
SDL Persists App Data after Suspend before Ignition Off
![OnSDLPersistenceComplete](./assets/OnSDLPersistenceComplete.png)
|||

#### JSON Example Notification
```json
{
	"jsonrpc" : "2.0",
	"method" : "BasicCommunication.OnSDLPersistenceComplete"
}
```
