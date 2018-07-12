## GetInteriorVehicleData

Type
: Function

Sender
: SDL

Purpose
: To read RC module status data. The same function is used to subscribe/unsubscribe to RC module status/setting change notifications.

GetInteriorVehicleData is a request originated by a Remote Control Mobile Application.  
If the parameter `subscribe` is set to `true`, the mobile application has requested to subscribe to the module data defined by the [`moduleType`](../../common/enums/#moduletype) parameter.  
SDL maintains the `moduleType` subscription status as a whole. SDL needs to subscribe to a module if there is at least one app that subscribes to the module. SDL needs to unsubscribe from a module if no apps subscribe to the module.  

SDL forwards a GetInteriorVehicleData request to HMI only if there is no cached data available for the requested `moduleType` or it needs to unsubscribe to the module from HMI.  
Otherwise, SDL responds to the request with the cached data without forwarding it to HMI.

The HMI should only return interior vehicle data that corresponds to the request`moduleType`. For example, if `moduleType = CLIMATE`, only return [`ClimateControlData`](../../common/structs/#climatecontroldata) and do not return [`RadioControlData`](../../common/structs/#radiocontroldata). 

### Request

#### Parameters

|Name|Type|Mandatory|Additional|
|:---|:---|:--------|:---------|
|moduleType|[Common.ModuleType](../../common/enums/#moduletype)|true||
|subscribe|Boolean|false|defvalue="false"|

### Response

#### Parameters

|Name|Type|Mandatory|Additional|
|:---|:---|:--------|:---------|
|moduleData|[Common.ModuleData](../../common/structs/#moduledata)|true||
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
        "moduleType": "CLIMATE",
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
