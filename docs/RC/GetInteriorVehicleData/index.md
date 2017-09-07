## GetInteriorVehicleData

Type
: Function

Sender
: SDL

Purpose
: To read RC module status data. The same function is used to subscribe/unsubscribe on RC module status/setting change notifications.

### Request

#### Parameters

|Name|Type|Mandatory|Additional|
|:---|:---|:--------|:---------|
|moduleType|[Common.ModuleType](/docs/Common/Enums/index.md)|true||
|subscribe|Boolean|false|defvalue="false"|
|appID|Integer|true||

### Response

#### Parameters

|Name|Type|Mandatory|Additional|
|:---|:---|:--------|:---------|
|moduleData|[Common.ModuleData](/docs/Common/Structs/index.md)|true||
|isSubscribed|Boolean|false||

### Sequence Diagrams

|||
GetInteriorVehicleData
![GetInteriorVehicleData](assets/GetInteriorVehicleData.png)
|||

### Example Request

```json
{
    "id": 122,
    "jsonrpc": "2.0",
    "method": "RC.GetInteriorVehicleData",
    "params": {
        "appID": 1093636990,
        "moduleType": "CLIMATE"
        "subscribe": true
    }
}
```

### Example Response

```json
{
    "id": 122,
    "jsonrpc": "2.0",
    "result": {
        "code": 0,
        "isSubscribed": true,
        "method": "RC.GetInteriorVehicleData",
        "moduleData": {
            "climateControlData": {
                "acEnable": true,
                "acMaxEnable": true,
                "autoModeEnable": true,
                "circulateAirEnable": true,
                "currentTemperature": {
                    "unit": "FAHRENHEIT",
                    "value": 20.1
                },
                "defrostZone": "FRONT",
                "desiredTemperature": {
                    "unit": "CELSIUS",
                    "value": 10.5
                },
                "dualModeEnable": true,
                "fanSpeed": 50,
                "ventilationMode": "BOTH"
            },
            "moduleType": "CLIMATE"
        }
    }
}

```

### Example Error

```json
{
    "error": {
        "code": 2,
        "data": {
            "method": "RC.GetInteriorVehicleData"
        },
        "message": "Unknown module type"
    },
    "id": 122,
    "jsonrpc": "2.0"
}
```
