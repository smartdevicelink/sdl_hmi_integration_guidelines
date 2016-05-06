## OnAppUnregistered

Type
: Notification

Sender
: SDL

Purpose
: Inform the HMI that an application has unregistered.

### Notification

#### Parameters

|Name|Type|Mandatory|Additional|
|:---|:---|:--------|:---------|
|unexpectedDisconnect|Boolean|true||
|appID|Integer|true||

### Sequence Diagrams
|||
Active App Unregistered
![OnAppUnregistered](./assets/OnAppUnregistered.png)
|||

#### JSON Example Notification
```json
{
	"jsonrpc" : "2.0",
	"method" : "BasicCommunication.OnAppUnregistered",
	"params" :
	{
		"appID" : 65539,
      "unexpectedDisconnect":"false"
	}
}
```
