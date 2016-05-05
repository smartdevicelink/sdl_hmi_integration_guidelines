## StopStream


### Request

#### Parameters

|Name|Type|Mandatory|Additional|Description|
|:---|:---|:--------|:---------|:----------|
|appID|Integer|true|||

### Response

#### Parameters

This RPC has no additional parameter requirements

### Sequence Diagrams
|||
StopStream
![StopStream](./assets/StopStream.jpg)
|||

### Example Request

```json
{
	"jsonrpc" : "2.0",
	"method" : "Navigation.StopStream",
	"params" :  
	{
		"appID" : 65674
	}
}
```
### Example Response

```json
{
	"id" : 176,
	"jsonrpc" : "2.0",
	"result" :
	{
		"code" : 0,
		"method" : "Navigation.StopStream"
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
		"code" : 22,
		"message" : "Stop stream failed or some other error occurred",
		"data" :
		{
			"method" : "Navigation.StopStream"
		}
	}
}
```
