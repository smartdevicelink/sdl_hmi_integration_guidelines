## DeleteCommand


### Request

#### Parameters

|Name|Type|Mandatory|Additional|Description|
|:---|:---|:--------|:---------|:----------|
|cmdID|Integer|true|minvalue: 0<br>maxvalue: 2000000000||
|appID|Integer|true|||

### Response

#### Parameters

This RPC has no additional parameter requirements

### Sequence Diagrams
|||
Delete Command with Menu Open
![DeleteCommand](./assets/DeleteCommandMenuOpen.png)
|||
|||
Delete Command Application Inactive
![DeleteCommand](./assets/DeleteCommandAppInactive.png)
|||

### Example Request

```json
{
	"id" : 70,
	"jsonrpc" : "2.0",
	"method" : "UI. DeleteCommand",
	"params" :
	{
		"cmdID" : 2318,
		"appID" : 65409
	}
}
```
### Example Response

```json
{
	"id" : 70,
	"jsonrpc" : "2.0",
	"result" :
	{
		"code" : 0,
		"method" : "UI. DeleteCommand"
	}
}
```

### Example Error

```json
{
	"id" : 70,
	"jsonrpc" : "2.0",
	"error" :
	{
		"code" : 13,
		"message" : "One of the provided IDs is not valid",
		"data" :
		{
			"UI. DeleteCommand"
		}
	}
}
```
