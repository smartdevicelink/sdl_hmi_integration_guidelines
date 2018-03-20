## UnsubscribeVehicleData

Type
: Function

Sender
: SDL

Purpose
: Unsubscribe from periodic vehicle data type updates

### Request

#### Parameters

|Name|Type|Mandatory|Additional|
|:---|:---|:--------|:---------|
|appID|Integer|true||
|gps|Boolean|false||
|speed|Boolean|false||
|rpm|Boolean|false||
|fuelLevel|Boolean|false||
|fuelLevel_State|Boolean|false||
|instantFuelConsumption|Boolean|false||
|externalTemperature|Boolean|false||
|prndl|Boolean|false||
|tirePressure|Boolean|false||
|odometer|Boolean|false||
|beltStatus|Boolean|false||
|bodyInformation|Boolean|false||
|deviceStatus|Boolean|false||
|driverBraking|Boolean|false||
|wiperStatus|Boolean|false||
|headLampStatus|Boolean|false||
|engineTorque|Boolean|false||
|accPedalPosition|Boolean|false||
|steeringWheelAngle|Boolean|false||
|eCallInfo|Boolean|false||
|airbagStatus|Boolean|false||
|emergencyEvent|Boolean|false||
|clusterModeStatus|Boolean|false||
|myKey|Boolean|false||
|fuelRange|Boolean|false||
|engineOilLife|Boolean|false||

### Response

#### Parameters

|Name|Type|Mandatory|Additional|
|:---|:---|:--------|:---------|
|gps|[Common.VehicleDataResult](../../common/structs/#vehicledataresult)|false||
|speed|[Common.VehicleDataResult](../../common/structs/#vehicledataresult)|false||
|rpm|[Common.VehicleDataResult](../../common/structs/#vehicledataresult)|false||
|fuelLevel|[Common.VehicleDataResult](../../common/structs/#vehicledataresult)|false||
|fuelLevel_State|[Common.VehicleDataResult](../../common/structs/#vehicledataresult)|false||
|instantFuelConsumption|[Common.VehicleDataResult](../../common/structs/#vehicledataresult)|false||
|externalTemperature|[Common.VehicleDataResult](../../common/structs/#vehicledataresult)|false||
|prndl|[Common.VehicleDataResult](../../common/structs/#vehicledataresult)|false||
|tirePressure|[Common.VehicleDataResult](../../common/structs/#vehicledataresult)|false||
|odometer|[Common.VehicleDataResult](../../common/structs/#vehicledataresult)|false||
|beltStatus|[Common.VehicleDataResult](../../common/structs/#vehicledataresult)|false||
|bodyInformation|[Common.VehicleDataResult](../../common/structs/#vehicledataresult)|false||
|deviceStatus|[Common.VehicleDataResult](../../common/structs/#vehicledataresult)|false||
|driverBraking|[Common.VehicleDataResult](../../common/structs/#vehicledataresult)|false||
|wiperStatus|[Common.VehicleDataResult](../../common/structs/#vehicledataresult)|false||
|headLampStatus|[Common.VehicleDataResult](../../common/structs/#vehicledataresult)|false||
|engineTorque|[Common.VehicleDataResult](../../common/structs/#vehicledataresult)|false||
|accPedalPosition|[Common.VehicleDataResult](../../common/structs/#vehicledataresult)|false||
|steeringWheelAngle|[Common.VehicleDataResult](../../common/structs/#vehicledataresult)|false||
|eCallInfo|[Common.VehicleDataResult](../../common/structs/#vehicledataresult)|false||
|airbagStatus|[Common.VehicleDataResult](../../common/structs/#vehicledataresult)|false||
|emergencyEvent|[Common.VehicleDataResult](../../common/structs/#vehicledataresult)|false||
|clusterModes|[Common.VehicleDataResult](../../common/structs/#vehicledataresult)|false||
|myKey|[Common.VehicleDataResult](../../common/structs/#vehicledataresult)|false||  
|fuelRange|[Common.VehicleDataResult](../../common/structs/#vehicledataresult)|false||
|engineOilLife|[Common.VehicleDataResult](../../common/structs/#vehicledataresult)|false||

### Sequence Diagrams
|||
UnsubscribeVehicleData
![UnsubscribeVehicleData](./assets/UnsubscribeVehicleData.jpg)
|||
|||
UnsubscribeVehicleData unexpected disconnect
![UnsubscribeVehicleData](./assets/UnsubscribeVehicleDataDisconnect.jpg)
|||

### Example Request

```json
{
  "id" : 139,
  "jsonrpc" : "2.0",
  "method" : "VehicleInfo.UnsubscribeVehicleData",
  "params" :
  {
    "gps" : true,
    "speed" : true,
    "fuelLevel_State" : true,
    "externalTemperature" : true,
    "prndl" : true,
    "tirePressure" : true,
    "odometer" : true,
    "beltStatus" : true,
    "bodyInformation" : true,
    "deviceStatus" : true,
    "wiperStatus" : true,
    "headLampStatus" : true,
    "accPedalPosition" : true,

  }
}
```
### Example Response

```json

  "id" : 139,
  "jsonrpc" : "2.0",
  "result" :
  {
    "gps" :
    {
      "dataType" : VEHICLEDATA_GPS,
      "resultCode" : SUCCESS
    },

    "speed" :
    {
      "dataType" : VEHICLEDATA_SPEED,
      "resultCode" : DATA_NOT_SUBSCRIBED
    },

    "fuelLevel_State" :
    {
      "dataType" : VEHICLEDATA_FUELLEVEL,
      "resultCode" : SUCCESS
    },

    "externalTemperature" :
    {
      "dataType" : VEHICLEDATA_EXTERNTEMP,
      "resultCode" : DATA_NOT_SUBSCRIBED
    },

    "prndl" :
    {
      "dataType" : VEHICLEDATA_PRNDL,
      "resultCode" : DATA_NOT_SUBSCRIBED
    },

    "tirePressure" :
    {
      "dataType" : VEHICLEDATA_TIREPRESSURE,
      "resultCode" : SUCCESS
    },

    "odometer" :
    {
      "dataType" : VEHICLEDATA_odometer,
      "resultCode" : SUCCESS
    },

    "beltStatus" :
    {
      "dataType" : VEHICLEDATA_BELTSTATUS,
      "resultCode" : SUCCESS
    },

    "bodyInformation" :
    {
      "dataType" : VEHICLEDATA_BODYINFO,
      "resultCode" : SUCCESS
    },

    "deviceStatus" :
    {
      "dataType" : VEHICLEDATA_DEVICESTATUS,
      "resultCode" : DATA_NOT_SUBSCRIBED
    },

    "wiperStatus" :
    {
      "dataType" : VEHICLEDATA_WIPERSTATUS,
      "resultCode" : SUCCESS
    },

    "headLampStatus" :
    {
      "dataType" : HEADLAMPSTATUS,
      "resultCode" : SUCCESS
    },

    "accPedalPosition" :
    {
      "dataType" : VEHICLEDATA_ACCPEDAL,
      "resultCode" : DATA_NOT_SUBSCRIBED
    },

    "code" : 0,
    "method" : "VehicleInfo.UnsubscribeVehicleData"
  }
}
```

### Example Error

```json
{
  "id" : 139,
  "jsonrpc" : "2.0",
  "error" :
  {
    "code" : 22,
    "message" : "An unknown error occurred",
    "data" :
    {
      "method" : "VehicleInfo.UnsubscribeVehicleData"
    }
  }
}
```
