## OnAppActivated


### Notification

#### Parameters

|Name|Type|Mandatory|Additional|Description|
|:---|:---|:--------|:---------|:----------|
|appID|Integer|true|||

### Sequence Diagrams
|||
User Activates App
![OnAppActivated](./assets/OnAppActivated.png)
|||

#### JSON Example Notification
```json
{
	"jsonrpc" : "2.0",
	"method" : "BasicCommunication.OnAppActivated",
	"params" :
	{
		"appID" : 65544
	}
}
```
