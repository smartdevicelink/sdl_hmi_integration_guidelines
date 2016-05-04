## OnAppDeactivated


### Notification

#### Parameters

|Name|Type|Mandatory|Additional|Description|
|:---|:---|:--------|:---------|:----------|
|appID|Integer|true|||
|reason|Common.DeactivateReason|true|||

#### DeactivateReason

|Name|Value|
|:---|:----|
|AUDIO|0|
|PHONECALL|1|
|NAVIGATIONMAP|2|
|PHONEMENU|3|
|SYNCSETTINGS|4|
|GENERAL|5|

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
