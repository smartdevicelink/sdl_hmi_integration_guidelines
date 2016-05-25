## SubscribeVehicleData

Type
: Function

Sender
: SDL

Purpose
: Subscribe to periodic vehicle data type updates

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

### Response

#### Parameters

|Name|Type|Mandatory|Additional|
|:---|:---|:--------|:---------|
|gps|[Common.VehicleDataResult](../../Common/Structs/index.md#vehicledataresult)|false||
|speed|[Common.VehicleDataResult](../../Common/Structs/index.md#vehicledataresult)|false||
|rpm|[Common.VehicleDataResult](../../Common/Structs/index.md#vehicledataresult)|false||
|fuelLevel|[Common.VehicleDataResult](../../Common/Structs/index.md#vehicledataresult)|false||
|fuelLevel_State|[Common.VehicleDataResult](../../Common/Structs/index.md#vehicledataresult)|false||
|instantFuelConsumption|[Common.VehicleDataResult](../../Common/Structs/index.md#vehicledataresult)|false||
|externalTemperature|[Common.VehicleDataResult](../../Common/Structs/index.md#vehicledataresult)|false||
|prndl|[Common.VehicleDataResult](../../Common/Structs/index.md#vehicledataresult)|false||
|tirePressure|[Common.VehicleDataResult](../../Common/Structs/index.md#vehicledataresult)|false||
|odometer|[Common.VehicleDataResult](../../Common/Structs/index.md#vehicledataresult)|false||
|beltStatus|[Common.VehicleDataResult](../../Common/Structs/index.md#vehicledataresult)|false||
|bodyInformation|[Common.VehicleDataResult](../../Common/Structs/index.md#vehicledataresult)|false||
|deviceStatus|[Common.VehicleDataResult](../../Common/Structs/index.md#vehicledataresult)|false||
|driverBraking|[Common.VehicleDataResult](../../Common/Structs/index.md#vehicledataresult)|false||
|wiperStatus|[Common.VehicleDataResult](../../Common/Structs/index.md#vehicledataresult)|false||
|headLampStatus|[Common.VehicleDataResult](../../Common/Structs/index.md#vehicledataresult)|false||
|engineTorque|[Common.VehicleDataResult](../../Common/Structs/index.md#vehicledataresult)|false||
|accPedalPosition|[Common.VehicleDataResult](../../Common/Structs/index.md#vehicledataresult)|false||
|steeringWheelAngle|[Common.VehicleDataResult](../../Common/Structs/index.md#vehicledataresult)|false||
|eCallInfo|[Common.VehicleDataResult](../../Common/Structs/index.md#vehicledataresult)|false||
|airbagStatus|[Common.VehicleDataResult](../../Common/Structs/index.md#vehicledataresult)|false||
|emergencyEvent|[Common.VehicleDataResult](../../Common/Structs/index.md#vehicledataresult)|false||
|clusterModes|[Common.VehicleDataResult](../../Common/Structs/index.md#vehicledataresult)|false||
|myKey|[Common.VehicleDataResult](../../Common/Structs/index.md#vehicledataresult)|false||

### Sequence Diagrams
|||
SubscribeVehicleData
![SubscribeVehicleData](./assets/SubscribeVehicleData.jpg)
|||

### Example Request

```json
{
  "id" : 139,
  "jsonrpc" : "2.0",
  "method" : "VehicleInfo.SubscribeVehicleData",
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
{
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
      "resultCode" : DATA_ALREADY_SUBSCRIBED
    },

    "fuelLevel_State" :
    {
      "dataType" : VEHICLEDATA_FUELLEVEL,
      "resultCode" : SUCCESS
    },

    "externalTemperature" :
    {
      "dataType" : VEHICLEDATA_EXTERNTEMP,
      "resultCode" : VEHICLE_DATA_NOT_AVAILABLE
    },

    "prndl" :
    {
      "dataType" : VEHICLEDATA_PRNDL,
      "resultCode" : VEHICLE_DATA_NOT_AVAILABLE
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
      "resultCode" : DATA_ALREADY_SUBSCRIBED
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
      "resultCode" : VEHICLE_DATA_NOT_AVAILABLE
    },

    "code" : 0,
    "method" : "VehicleInfo.SubscribeVehicleData"
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
    "code" : 6,
    "message" : "All of requested data types is subscribed already",
    "data" :
    {
      "method" : "VehicleInfo.SubscribeVehicleData"
    }
  }
}
```
