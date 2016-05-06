## OnAppDeactivated


### Notification

#### Parameters

|Name|Type|Mandatory|Additional|
|:---|:---|:--------|:---------|
|appID|Integer|true||
|reason|[Common.DeactivateReason](../../Common/Enums/index.md#deactivatereason)|true||

### Sequence Diagrams
|||
User Switches Apps
![OnAppDeactivated](./assets/OnAppDeactivated.png)
|||

#### JSON Example Notification
```json
{
	"jsonrpc" : "2.0",
	"method" : "BasicCommunication.OnAppDeactivated",
	"params" :
	{
		"appID" : 65544,
		"reason" : PHONECALL
	}
}
```
