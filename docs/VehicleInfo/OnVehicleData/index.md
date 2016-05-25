## OnVehicleData

Type
: Notification

Sender
: HMI

Purpose
: Inform SDL about changes to subscribed vehicle data values.

### Notification

#### Parameters

|Name|Type|Mandatory|Additional|
|:---|:---|:--------|:---------|
|gps|[Common.GPSData](../../common/structs/index.md#gpsdata)|false||
|speed|Float|false|minvalue: 0<br>maxvalue: 700|
|rpm|Integer|false|minvalue: 0<br>maxvalue: 20000|
|fuelLevel|Float|false|minvalue: -6<br>maxvalue: 106|
|fuelLevel_State|[Common.ComponentVolumeStatus](../../common/enums/index.md#componentvolumestatus)|false||
|instantFuelConsumption|Float|false|minvalue: 0<br>maxvalue: 25575|
|externalTemperature|Float|false|minvalue: -40<br>maxvalue: 100|
|vin|String|false|maxlength: 17|
|prndl|[Common.PRNDL](../../common/enums/index.md#prndl)|false||
|tirePressure|[Common.TireStatus](../../common/structs/index.md#tirestatus)|false||
|odometer|Integer|false|minvalue: 0<br>maxvalue: 17000000|
|beltStatus|[Common.BeltStatus](../../common/structs/index.md#beltstatus)|false||
|bodyInformation|[Common.BodyInformation](../../common/structs/index.md#bodyinformation)|false||
|deviceStatus|[Common.DeviceStatus](../../common/structs/index.md#devicestatus)|false||
|driverBraking|[Common.VehicleDataEventStatus](../../common/enums/index.md#vehicledataeventstatus)|false||
|wiperStatus|[Common.WiperStatus](../../common/enums/index.md#wiperstatus)|false||
|headLampStatus|[Common.HeadLampStatus](../../common/structs/index.md#headlampstatus)|false||
|engineTorque|Float|false|minvalue: -1000<br>maxvalue: 2000|
|accPedalPosition|Float|false|minvalue: 0<br>maxvalue: 100|
|steeringWheelAngle|Float|false|minvalue: -2000<br>maxvalue: 2000|
|eCallInfo|[Common.ECallInfo](../../common/structs/index.md#ecallinfo)|false||
|airbagStatus|[Common.AirbagStatus](../../common/structs/index.md#airbagstatus)|false||
|emergencyEvent|[Common.EmergencyEvent](../../common/structs/index.md#emergencyevent)|false||
|clusterModeStatus|[Common.ClusterModeStatus](../../common/structs/index.md#clustermodestatus)|false||
|myKey|[Common.MyKey](../../common/structs/index.md#mykey)|false||

### Sequence Diagrams
|||
OnVehicleData
![OnVehicleData](./assets/OnVehicleData.jpg)
|||

#### JSON Example Notification
```json
{
  "jsonrpc" : "2.0",
  "method" : "VehicleInfo.OnVehicleData",
  "params" :  
  {
    "speed" : 60,
    "externalTemperature" : -7,
    "prndl" : THIRD,
    "odometer" : 1066,
    "wiperStatus" : MAN_INT_ON,
    "accPedalPosition" : 70
  }
}
```
