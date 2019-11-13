## OnInteriorVehicleData

Type
: Notification

Sender
: HMI

Purpose
: Inform SDL about any changes in RC module settings.



The HMI must send RC.OnInteriorVehicleData notification to SDL when module settings were changed in case of button press event or after SetInteriorVehicledata request was processed.

!!! MUST

The HMI must always include a `moduleId` for a `ModuleData` in OnInteriorVehicleData notification.

The HMI must send RC.OnInteriorVehicleData notification with the current display mode to all mobile RC applications that are subscribed to the HMI settings  
if the driver (or other applications) or HMI itself change the display mode in the HMI settings.

!!!

### Notification

#### Parameters

|Name|Type|Mandatory|Additional|
|:---|:---|:--------|:---------|
|moduleData|[Common.ModuleData](../../common/structs/#moduledata)|true||

### Sequence Diagrams

|||
OnInteriorVehicledata
![OnInteriorVehicleData](assets/OnInteriorVehicleData.png)
|||

### JSON Message Examples

#### Example Notification

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
