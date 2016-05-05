## OnVideoDataStreaming


### Notification

#### Parameters

|Name|Type|Mandatory|Additional|Description|
|:---|:---|:--------|:---------|:----------|
|available|Boolean|true|||

### Sequence Diagrams
|||
OnVideoDataStreaming
![OnVideoDataStreaming](./assets/OnVideoDataStreaming.jpg)
|||

#### JSON Example Notification
```json
{
	"jsonrpc" : "2.0",
	"method" : "Navigation.OnVideoDataStreaming",
	"params" :  
	{
		"available" : true
	}
}
```
