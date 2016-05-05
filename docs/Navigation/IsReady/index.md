## IsReady

Type
: Function

Sender
: SDL

Purpose
: Request ready state of Navigation Module

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
IsReady
![IsReady](./assets/IsReady.png)
|||

### Example Request

```json
{
	"id" : 27,
	"jsonrpc" : "2.0",
	"method" : "Navigation.IsReady"
}
```
### Example Response

```json
{
	"id" : 27,
	"jsonrpc" : "2.0",
	"result" :
	{
		"availabe" : true,
		"code" : 0,
		"method" : "Navigation.IsReady"
	}
}
```

### Example Error

```json
{
	"id" : 27,
	"jsonrpc" : "2.0",
	"error" :
	{
		"code" : 22,
		"message" : "An unknown error has occurred",
		"data" :
		{
			"method" : "Navigation.IsReady"
		}
	}
}
```
