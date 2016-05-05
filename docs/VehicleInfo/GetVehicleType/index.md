## GetVehicleType


### Request

#### Parameters

|Name|Type|Mandatory|Additional|Description|
|:---|:---|:--------|:---------|:----------|

### Response

#### Parameters

|Name|Type|Mandatory|Additional|Description|
|:---|:---|:--------|:---------|:----------|
|vehicleType|Common.VehicleType|true|||

#### VehicleType

|Name|Type|Mandatory|Additional|Description|
|:---|:---|:--------|:---------|:----------|
|make|String|false|maxlength: 500||
|model|String|false|maxlength: 500||
|modelYear|String|false|maxlength: 500||
|trim|String|false|maxlength: 500||

### Sequence Diagrams
|||
GetVehicleType
![GetVehicleType](./assets/GetVehicleType.png)
|||

### Example Request

```json
{
	"id" : 21,
	"jsonrpc" : "2.0",
	"method" : "VehicleInfo.GetVehicleType"
}
```
### Example Response

```json
{
	"id" : 21,
	"jsonrpc" : "2.0",
	"result" :
	{
		"vehicleType" :
		[
			"make" : "Ford",
			"model" : "Fusion",
			"modelYear" : "2013",
			"trim" : "SE"
		]
		"code" : 0,
		"method" : "VehicleInfo.GetVehicleType"
	}
}
```

### Example Error

```json
{
	"id" : 21,
	"jsonrpc" : "2.0",
	"error" :
	{
		"code" : 9,
		"message" : "The requested data is not available",
		"data" :
		{
			"method" : "VehicleInfo.GetVehicleType"
		}
	}
}
```
