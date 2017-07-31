## GetInteriorVehicleDataConsent

Type
: Function

Sender
: SDL

Purpose
: Request for driver's permission to RC module for the specified application

RC.GetInteriorVehicleDataConsent must be sent to HMI in case application in HMILevel FULL requested access to RC module that is already in use by another application. 
HMI is expected to display a permission prompt to the driver showing the RC module and app details (for example, app's name).
The driver is expected to have an ability to grant or deny the permission.

!!! must

1. Access mode "ASK_DRIVER"
2. Application that requested access to RC module must be in HMILevel FULL
3. Requested module is not busy with executing request from another application

!!!

### Request

#### Parameters

|Name|Type|Mandatory|Additional|Description|
|:---|:---|:--------|:---------|:---------|
|moduleType|[Common.ModuleType](https://github.com/OlesiaV/sdl_hmi_integration_guidelines/blob/a118768fa9c6631e168f932919687196bd281f46/docs/Common/Enums/index.md)|true||The module type that the app requests to control|
|appID|Integer|true||ID of the application that triggers the permission prompt|

### Response

#### Parameters
|Name|Type|Mandatory|Additional|Description|
|:---|:---|:--------|:---------|:---------|
|allowed|Boolean|true||"true" - if the driver grants the permission for controlling to the named app; <br> "false" - in case the driver denies the permission for controlling to the named app.|

### Sequence Diagrams

|||
GetInteriorVehicleDataConsent
![GetInteriorVehicleDataConsent](https://github.com/OlesiaV/sdl_hmi_integration_guidelines/blob/sdl_rc_part3/docs/RC/GetInteriorVehicleDataConsent/accessories/GetInteriorVehicleDataConsent.png)
|||

### Example Request

```json
{
    "id": 38,
    "jsonrpc": "2.0",
    "method": "RC.GetInteriorVehicleDataConsent",
    "params": {
        "appID": 2032286926,
        "moduleType": "CLIMATE"
    }
}
```

### Example Response

```json
{
    "id": 38,
    "jsonrpc": "2.0",
    "result": {
        "allowed": true,
        "code": 0,
        "method": "RC.GetInteriorVehicleDataConsent"
    }
}
```

### Example Error

```json
{
    "error": {
        "code": 26,
        "data": {
            "method": "RC.GetInteriorVehicleDataConsent"
        },
        "message": "Info message"
    },
    "id": 38,
    "jsonrpc": "2.0"
}
```
