## OnCommand


### Notification

#### Parameters

|Name|Type|Mandatory|Additional|Description|
|:---|:---|:--------|:---------|:----------|
|cmdID|Integer|true|minvalue: 0<br>maxvalue: 2000000000||
|appID|Integer|true|||

### Sequence Diagrams
|||
OnCommand
![OnCommand](./assets/OnCommand.png)
|||

#### JSON Example Notification
```json
{
	"jsonrpc" : "2.0",
	"method" : "UI.OnCommand",
	"params" :
	{
		"cmdID" : 2318,
     "appID" : 65409
	}
}
```
