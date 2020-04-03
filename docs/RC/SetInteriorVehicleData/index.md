## SetInteriorVehicleData

Type
: Function

Sender
: SDL

Purpose
: Set RC module settings

RC.SetInteriorVehicleData represents a request from an application to change settings of requested RC module. This RPC can be sent to the HMI for an application that is registered with REMOTE_CONTROL appHMIType and in one of the following states: FULL, LIMITED, BACKGROUND. Module signed by the application in such request has to be available on HMI and allowed for control change settings

!!! must

  1. Modules sent by application must be available on HMI
  2. Access to control module settings is defined by access mode entered by user on HMI
  3. Module settings can be changed for settable parameters only
  4. Requested module items have to be available for such module on HMI
  
!!!

### Request

#### Parameters

|Name|Type|Mandatory|Additional|Description|
|:---|:---|:--------|:---------|:----------|
|moduleData|[Common.ModuleData](../../common/structs/#moduledata)|true| |The module type and data to set|
|appID|Integer|true| |Internal SDL-assigned ID of the related application|

### Response

#### Parameters

|Name|Type|Mandatory|Additional|Description|
|:---|:---|:--------|:---------|:----------|
|moduleData|[Common.ModuleData](../../common/structs/#moduledata)|true| | |

### Sequence Diagrams

|||
SetInteriorVehicleData
![SetInteriorVehicleData](./assets/SetInteriorVehicleData.png)
|||

|||
SetInteriorVehicleData-READ_ONLY
![SetInteriorVehicleData READ_ONLY](./assets/setInteriorVehicleData_READ_ONLY.png)
|||

### JSON Message Examples

#### Example Request

```json
{
    "id": 31,
    "jsonrpc": "2.0",
    "method": "RC.SetInteriorVehicleData",
    "params": {
        "appID": 306873852,
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

#### Example Response

```json
{
    "id": 31,
    "jsonrpc": "2.0",
    "result": {
        "code": 0,
        "method": "RC.SetInteriorVehicleData",
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

#### Example Error

```json
{
    "error": {
        "code": 26,
        "data": {
            "method": "RC.SetInteriorVehicleData"
        },
        "message": "Read only parameters received"
    },
    "id": 31,
    "jsonrpc": "2.0"
}
```
