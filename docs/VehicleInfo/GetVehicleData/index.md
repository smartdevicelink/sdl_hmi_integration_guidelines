## GetVehicleData

Type
: Function

Sender
: SDL

Purpose
: Get current values of specified vehicle data types.

### Request

#### Parameters

|Name|Type|Mandatory|Additional|
|:---|:---|:--------|:---------|
|gps|Boolean|false||
|speed|Boolean|false||
|rpm|Boolean|false||
|fuelLevel|Boolean|false||
|fuelLevel_State|Boolean|false||
|instantFuelConsumption|Boolean|false||
|externalTemperature|Boolean|false||
|vin|Boolean|false||
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
|appID|Integer|true||
|engineOilLife|Boolean|false||

### Response

#### Parameters

|Name|Type|Mandatory|Additional|
|:---|:---|:--------|:---------|
|gps|[Common.GPSData](../../common/structs/#gpsdata)|false||
|speed|Float|false|minvalue: 0<br>maxvalue: 700|
|rpm|Integer|false|minvalue: 0<br>maxvalue: 20000|
|fuelLevel|Float|false|minvalue: -6<br>maxvalue: 106|
|fuelLevel_State|[Common.ComponentVolumeStatus](../../common/enums/#componentvolumestatus)|false||
|instantFuelConsumption|Float|false|minvalue: 0<br>maxvalue: 25575|
|externalTemperature|Float|false|minvalue: -40<br>maxvalue: 100|
|vin|String|false|maxlength: 17|
|prndl|[Common.PRNDL](../../common/enums/#prndl)|false||
|tirePressure|[Common.TireStatus](../../common/structs/#tirestatus)|false||
|odometer|Integer|false|minvalue: 0<br>maxvalue: 17000000|
|beltStatus|[Common.BeltStatus](../../common/structs/#beltstatus)|false||
|bodyInformation|[Common.BodyInformation](../../common/structs/#bodyinformation)|false||
|deviceStatus|[Common.DeviceStatus](../../common/structs/#devicestatus)|false||
|driverBraking|[Common.VehicleDataEventStatus](../../common/enums/#vehicledataeventstatus)|false||
|wiperStatus|[Common.WiperStatus](../../common/enums/#wiperstatus)|false||
|headLampStatus|[Common.HeadLampStatus](../../common/structs/#headlampstatus)|false||
|engineTorque|Float|false|minvalue: -1000<br>maxvalue: 2000|
|accPedalPosition|Float|false|minvalue: 0<br>maxvalue: 100|
|steeringWheelAngle|Float|false|minvalue: -2000<br>maxvalue: 2000|
|eCallInfo|[Common.ECallInfo](../../common/structs/#ecallinfo)|false||
|airbagStatus|[Common.AirbagStatus](../../common/structs/#airbagstatus)|false||
|emergencyEvent|[Common.EmergencyEvent](../../common/structs/#emergencyevent)|false||
|clusterModeStatus|[Common.ClusterModeStatus](../../common/structs/#clustermodestatus)|false||
|myKey|[Common.MyKey](../../common/structs/#mykey)|false||  
|fuelRange|[Common.FuelRange](../../common/structs/#fuelrange)|false|minsize=0<br>maxsize=100<br>array=true|
|engineOilLife|Float|false|minvalue=0<br>maxvalue=100|

### Sequence Diagrams
|||
GetVehicleData
![GetVehicleData](./assets/GetVehicleData.jpg)
|||

### Example Request

```json
{
  "id" : 139,
  "jsonrpc" : "2.0",
  "method" : "VehicleInfo.GetVehicleData",
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
    [
      "longitudeDegrees" : 46.4774700,
      "latitudeDegrees" : 30.7326200,
      "utcYear" : 2013,
      "utcMonth" : 12,
      "utcDay" : 31,
      "utcHours" : 23,
      "utcMinutes" : 50,
      "utcSeconds" : 5,
      "compassDirection" : NORTH,
      "pdop" : 0.15,
      "hdop" : 1.01,
      "vdop" : 1.56,
      "actual" : true,
      "satellites" : 8,
      "dimension" : 3D,
      "altitude" : 47,
      "heading" : 0,
      "speed" : 90
    ],

    "speed" : 90,
    "fuelLevel_State" : LOW,
    "externalTemperature" : -5,
    "prndl" : FOURTH,
    "tirePressure" :
    [
        "pressureTelltale" : ON,
        "leftFront" : NORMAL,
        "rightFront" : NORMAL,
        "leftRear" : LOW,
        "rightRear" : UNKNOWN
    ],

    "odometer" : 1065,
    "beltStatus" :
    [
        "driverBeltDeployed" : YES,
        "passengerBeltDeployed" : YES,
    ],

    "bodyInformation" :
    [
        "parkBrakeActive" : false,
        "ignitionStableStatus" : IGNITION_SWITCH_STABLE,
        "ignitionStatus" : RUN
    ],
    "deviceStatus" :
    [
        "voiceRecOn" : false,
        "btIconOn" : false,
        "callActive" : false,
        "phoneRoaming" : false,
        "textMsgAvailable" : true,
        "battLevelStatus" : THREE_LEVEL_BARS,
        "stereoAudioOutputMuted" : true,
        "monoAudioOutputMuted" : false,
        "signalLevelStatus" : NOT_PROVIDED,
        "primaryAudioSource" : MOBILE_APP,
        "eCallEventActive" : false
    ],

    "wiperStatus" : OFF,
    "headLampStatus" :
    [
        "lowBeamsOn" : true,
        "highBeamsOn" : false
    ],

    "accPedalPosition" : 80,

    "code" : 0,
    "method" : "VehicleInfo.GetVehicleData"
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
    "code" : 9,
    "message" : "The requested data is not available",
    "data" :
    {
      "method" : "VehicleInfo.GetVehicleData"
    }
  }
}
```
