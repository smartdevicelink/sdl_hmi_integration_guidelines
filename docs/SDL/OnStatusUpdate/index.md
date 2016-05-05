## OnStatusUpdate

Type
: Notification

Sender
: SDL

Purpose
: Inform the HMI about the status of a policy table update.

### Notification

#### Parameters

|Name|Type|Mandatory|Additional|Description|
|:---|:---|:--------|:---------|:----------|
|status|Common.UpdateResult|true|||

#### UpdateResult

|Name|Value|
|:---|:----|
|UP_TO_DATE|0|
|UPDATING|1|
|UPDATE_NEEDED|2|

### Sequence Diagrams
|||
OnStatusUpdate
![OnStatusUpdate](./assets/OnStatusUpdate.jpg)
|||

#### JSON Example Notification
```json
{
	"jsonrpc" : "2.0",
	"method" : "SDL.OnStatusUpdate",
	"params" :  
	{
		"status" : "UPDATE_NEEDED"
	}
}
```
