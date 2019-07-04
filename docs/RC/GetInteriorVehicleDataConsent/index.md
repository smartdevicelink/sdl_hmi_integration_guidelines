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
1. HMI must prompt user to make selection of resource allocation
2. Respond to SDL with user choice within RC.GetInteriorVehicleDataConsent response
3. If user didn't make choice send GENERIC_ERROR to SDL
!!!

### Request

#### Parameters

|Name|Type|Mandatory|Additional|Description|
|:---|:---|:--------|:---------|:----------|
|moduleType|[Common.ModuleType](../../common/enums/#moduletype)|true| |The module type that the app requests to control|
|moduleIds|String|false|maxlength="100"|Ids of a module of same type, published by System Capability|
|appID|Integer|true| |ID of the application that triggers the permission prompt|

### Response

#### Parameters
|Name|Type|Mandatory|Additional|Description|
|:---|:---|:--------|:---------|:----------|
|allowed|Boolean|true|array="true"|"true" - if the driver grants the permission for controlling to the named app; <br> "false" - in case the driver denies the permission for controlling to the named app.|

### Sequence Diagrams

|||
GetInteriorVehicleDataConsent
![GetInteriorVehicleDataConsent](assets/GetInteriorVehicleDataConsent.png)
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
        "code": 10,
        "data": {
            "method": "RC.GetInteriorVehicleDataConsent"
        },
        "message": "No response from driver"
    },
    "id": 38,
    "jsonrpc": "2.0"
}
```
