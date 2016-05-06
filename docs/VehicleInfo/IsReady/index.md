## IsReady

Type
: Function

Sender
: SDL

Purpose
: Request ready state of the VehicleInfo Module

### Request

#### Parameters

|Name|Type|Mandatory|Additional|
|:---|:---|:--------|:---------|

### Response

#### Parameters

|Name|Type|Mandatory|Additional|
|:---|:---|:--------|:---------|
|available|Boolean|true||

### Sequence Diagrams
|||
IsReady
![IsReady](./assets/IsReady.png)
|||

### Example Request

```json
{
	"id" : 17,
	"jsonrpc" : "2.0",
	"method" : "VehicleInfo.IsReady"
}
```
### Example Response

```json
{
	"id" : 17,
	"jsonrpc" : "2.0",
	"result" :
	{
		"availabe" : true,
		"code" : 0,
		"method" : "VehicleInfo.IsReady"
	}
}
```

### Example Error

```json
{
	"id" : 17,
	"jsonrpc" : "2.0",
	"error" :
	{
		"code" : 9,
		"message" : "Data not available",
		"data" :
		{
			"method" : "VehicleInfo.IsReady"
		}
	}
}
```
