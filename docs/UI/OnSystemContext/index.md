## OnSystemContext

Type
: Notification

Sender
: HMI

Purpose
: Inform SDL about the current context of app interaction.

### Notification

#### Parameters

|Name|Type|Mandatory|Additional|Description|
|:---|:---|:--------|:---------|:----------|
|systemContext|Common.SystemContext|true|||
|appID|Integer|false|||

#### SystemContext

|Name|Value|
|:---|:----|
|MAIN|0|
|VRSESSION|1|
|MENU|2|
|HMI_OBSCURED|3|
|ALERT|4|

### Sequence Diagrams
|||
OnSystemContext for different HMI States
![OnSystemContext](./assets/OnSystemContext.png)
|||

#### JSON Example Notification
```json
{
	"jsonrpc" : "2.0",
	"method" : "UI.OnSystemContext",
	"params" :
	{
		"systemContext" : "VRSESSION"
	}
}
```
