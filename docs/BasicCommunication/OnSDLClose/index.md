## OnSDLClose

Type
: Notification

Sender
: SDL

Purpose
: Inform the HMI that SDL is ready to be terminated by the system.


### Notification

### Sequence Diagrams
|||
OnSDLClose Ingition Cycle
![OnSDLClose](./assets/OnSDLCloseIgnition.png)
|||
|||
OnSDLClose Master Reset
![OnSDLClose](./assets/OnSDLCLoseReset.png)
|||

#### JSON Example Notification
```json
{
	"jsonrpc" : "2.0",
	"method" : "BasicCommunication.OnSDLClose"
}
```
