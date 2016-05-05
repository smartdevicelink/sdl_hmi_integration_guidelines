## IsReady


### Request

#### Parameters

|Name|Type|Mandatory|Additional|Description|
|:---|:---|:--------|:---------|:----------|

### Response

#### Parameters

|Name|Type|Mandatory|Additional|Description|
|:---|:---|:--------|:---------|:----------|
|available|Boolean|true|||

### Sequence Diagrams
|||
UI Component Ready
![IsReady](./assets/IsReady.png)
|||

### Example Request

```json
{
	"id" : 8,
	"jsonrpc" : "2.0",
	"method" : "UI.IsReady"
}
```
### Example Response

```json
{
	"id" : 8,
	"jsonrpc" : "2.0",
	"result" :
	{
		"available" : false,
		"code" : 0,
		"method" : "UI.IsReady"
	}
}
```

### Example Error

```json
{
	"id" : 8,
	"jsonrpc" : "2.0",
	"error" :
	{
		"code" : 22,
		"message" : " HMI doesn’t have the information about UI availability or some failure occurred ",
		"data" :
		{
			"method" : "UI.IsReady"
		}
	}
}
```
