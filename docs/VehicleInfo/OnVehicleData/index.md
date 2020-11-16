## OnVehicleData

Type
: Notification

Sender
: HMI

Purpose
: Inform SDL about changes to subscribed vehicle data values.

!!! must

Send OnVehicleData notification with the correct structure per RPC spec/schema items defined in PT

!!!

!!! note

#### CloudAppVehicleID

* An optional parameter used by cloud apps or the policy server to identify the head unit
* Could be used by a cloud app to identify an incoming connection from core
* Could be used by a policy server to index cloud app configurations for a specific head unit

The HMI will have to update this field if the user chooses to reset this value (in case the vehicle changes owners)

!!!

### Notification

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
|turnSignal|[Common.TurnSignal](../../common/enums/#turnsignal)|false||
|fuelRange|[Common.FuelRange](../../common/structs/#fuelrange)|false|array: true<br>minsize: 0<br>maxsize: 100|
|engineOilLife|Float|false|minvalue: 0<br>maxvalue: 100|
|electronicParkBrakeStatus|[Common.ElectronicParkBrakeStatus](../../common/enums/#electronicparkbrakestatus)|false||
|cloudAppVehicleID|String|false||
|climateData|[Common.ClimateData](../../common/structs/#climatedata)|false||

### Sequence Diagrams

|||
OnVehicleData
![OnVehicleData](./assets/OnVehicleData.jpg)
|||

### JSON Message Examples

#### Example Notification

```json
{
  "jsonrpc" : "2.0",
  "method" : "VehicleInfo.OnVehicleData",
  "params" :  
  {
    "speed" : 60,
    "externalTemperature" : -7,
    "prndl" : "THIRD",
    "odometer" : 1066,
    "wiperStatus" : "MAN_INT_ON",
    "accPedalPosition" : 70
  }
}
```
