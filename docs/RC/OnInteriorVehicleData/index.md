## OnInteriorVehicleData

Type
: Notification

Sender
: HMI

Purpose
: Inform SDL about any changes in RC module settings.

!!! must

The HMI must send RC.OnInteriorVehicleData notification to SDL when module settings were changed in case of button press event or after SetInteriorVehicledata request was processed

The HMI must send RC.OnInteriorVehicleData notification with the current display mode to all mobile RC applications that are subscribed to the HMI settings  
if the driver (or other applications) or HMI itself change the display mode in the HMI settings.
!!!

### Notification

#### Parameters

|Name|Type|Mandatory|Additional|
|:---|:---|:--------|:---------|
|moduleData|[Common.ModuleData](docs/Common/Structs/index.md)|true||

### Sequence Diagrams

|||
OnInteriorVehicledata
![OnInteriorVehicleData](assets/OnInteriorVehicleData.png)
|||

#### JSON Example Notification
```json
{
    "jsonrpc": "2.0",
    "method": "RC.OnInteriorVehicleData",
    "params": {
        "moduleData": {
            "climateControlData": {
                "acEnable": false,
                "acMaxEnable": false,
                "autoModeEnable": true,
                "circulateAirEnable": false,
                "currentTemperature": {
                    "unit": "FAHRENHEIT",
                    "value": 44.3
                },
                "defrostZone": "ALL",
                "desiredTemperature": {
                    "unit": "CELSIUS",
                    "value": 22.6
                },
                "dualModeEnable": true,
                "fanSpeed": 65,
                "ventilationMode": "UPPER"
            },
            "moduleType": "CLIMATE"
        }
    }
}
```
