## OnEmergencyEvent


### Notification

#### Parameters

|Name|Type|Mandatory|Additional|Description|
|:---|:---|:--------|:---------|:----------|
|enabled|Boolean|true|||

### Sequence Diagrams
|||
Emergency Event Activated
![OnEmergencyEvent](./assets/OnEmergencyEvent.png)
|||

#### JSON Example Notification
```json
{
	"jsonrpc" : "2.0",
	"method" : "BasicCommunication. OnEmergencyEvent"
     "params" :
	{
				"enabled" : "true"

	}

}
```
