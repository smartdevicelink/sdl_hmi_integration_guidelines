## GetStatusUpdate


### Request

#### Parameters

|Name|Type|Mandatory|Additional|Description|
|:---|:---|:--------|:---------|:----------|

### Response

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
GetStatusUpdate
![GetStatusUpdate](./assets/GetStatusUpdate.jpg)
|||

### Example Request

```json
{
	"id" : 176,
	"jsonrpc" : "2.0",
	"method" : "SDL.GetStatusUpdate",
}
```
### Example Response

```json
{
	"id" : 176,
	"jsonrpc" : "2.0",
	"result" :
	{
		"status" : "UPDATE_NEEDED"
		"code" : 0,
		"method" : "SDL.GetStatusUpdate"
	}
}
```

### Example Error

```json
{
	"id" : 176,
	"jsonrpc" : "2.0",
	"error" :
	{
		"code" :22,
		"message" : "Some error occured",
		"data" :
		{
			"method" : "SDL.GetStatusUpdate"
		}
	}
}
```
