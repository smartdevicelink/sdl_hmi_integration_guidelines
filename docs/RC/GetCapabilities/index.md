## GetCapabilities

Type
: Function

Sender
: SDL

Purpose
: Inform SDL of the Remote Control capabilities of HMI, invoked at system startup.

### Request

#### Parameters

|Name|Type|Mandatory|Additional|
|:---|:---|:--------|:---------|

### Response

#### Parameters

|Name|Type|Mandatory|Additional|
|:--------|:--------|:---|:---------|
|remoteControlCapability|[Common.RemoteControlCapabilities](docs/Common/Structs/index.md)|false|See RemoteControlCapabilities, all available RC modules and buttons shall be returned|

### Sequence Diagrams

|||
GetCapabilities
![GetCapabilities](assets/IsReady_GetCapabilities.png)
|||

### Example Request

```json
{
            "id":22,
            "jsonrpc":"2.0",
            "method":"RC.GetCapabilities"
}
```

### Example Response

```json
{
    "id": 22,
    "jsonrpc": "2.0",
    "result": {
        "code": 0,
        "method": "RC.GetCapabilities",
        "remoteControlCapability": {
            "buttonCapabilities": [
                {
                    "longPressAvailable": true,
                    "name": "AC_MAX",
                    "shortPressAvailable": true,
                    "upDownAvailable": true
                },
                {
                    "longPressAvailable": true,
                    "name": "AC",
                    "shortPressAvailable": true,
                    "upDownAvailable": true
                },
                {
                    "longPressAvailable": true,
                    "name": "RECIRCULATE",
                    "shortPressAvailable": true,
                    "upDownAvailable": true
                },
                {
                    "longPressAvailable": true,
                    "name": "FAN_UP",
                    "shortPressAvailable": true,
                    "upDownAvailable": true
                },
                {
                    "longPressAvailable": true,
                    "name": "FAN_DOWN",
                    "shortPressAvailable": true,
                    "upDownAvailable": true
                },
                {
                    "longPressAvailable": true,
                    "name": "TEMP_UP",
                    "shortPressAvailable": true,
                    "upDownAvailable": true
                },
                {
                    "longPressAvailable": true,
                    "name": "TEMP_DOWN",
                    "shortPressAvailable": true,
                    "upDownAvailable": true
                },
                {
                    "longPressAvailable": true,
                    "name": "DEFROST_MAX",
                    "shortPressAvailable": true,
                    "upDownAvailable": true
                },
                {
                    "longPressAvailable": true,
                    "name": "DEFROST",
                    "shortPressAvailable": true,
                    "upDownAvailable": true
                },
                {
                    "longPressAvailable": true,
                    "name": "DEFROST_REAR",
                    "shortPressAvailable": true,
                    "upDownAvailable": true
                },
                {
                    "longPressAvailable": true,
                    "name": "UPPER_VENT",
                    "shortPressAvailable": true,
                    "upDownAvailable": true
                },
                {
                    "longPressAvailable": true,
                    "name": "LOWER_VENT",
                    "shortPressAvailable": true,
                    "upDownAvailable": true
                },
                {
                    "longPressAvailable": true,
                    "name": "VOLUME_UP",
                    "shortPressAvailable": true,
                    "upDownAvailable": true
                },
                {
                    "longPressAvailable": true,
                    "name": "VOLUME_DOWN",
                    "shortPressAvailable": true,
                    "upDownAvailable": true
                },
                {
                    "longPressAvailable": true,
                    "name": "EJECT",
                    "shortPressAvailable": true,
                    "upDownAvailable": true
                },
                {
                    "longPressAvailable": true,
                    "name": "SOURCE",
                    "shortPressAvailable": true,
                    "upDownAvailable": true
                },
                {
                    "longPressAvailable": true,
                    "name": "SHUFFLE",
                    "shortPressAvailable": true,
                    "upDownAvailable": true
                },
                {
                    "longPressAvailable": true,
                    "name": "REPEAT",
                    "shortPressAvailable": true,
                    "upDownAvailable": true
                }
            ],
            "climateControlCapabilities": [
                {
                    "acEnableAvailable": true,
                    "acMaxEnableAvailable": true,
                    "autoModeEnableAvailable": true,
                    "circulateAirEnableAvailable": true,
                    "currentTemperatureAvailable": true,
                    "defrostZone": [
                        "FRONT",
                        "REAR",
                        "ALL",
                        "NONE"
                    ],
                    "defrostZoneAvailable": true,
                    "desiredTemperatureAvailable": true,
                    "dualModeEnableAvailable": true,
                    "fanSpeedAvailable": true,
                    "moduleName": "Climate",
                    "ventilationMode": [
                        "UPPER",
                        "LOWER",
                        "BOTH",
                        "NONE"
                    ],
                    "ventilationModeAvailable": true
                }
            ],
            "radioControlCapabilities": [
                {
                    "availableHDsAvailable": true,
                    "hdChannelAvailable": true,
                    "moduleName": "Radio",
                    "radioBandAvailable": true,
                    "radioEnableAvailable": true,
                    "radioFrequencyAvailable": true,
                    "rdsDataAvailable": true,
                    "signalChangeThresholdAvailable": true,
                    "signalStrengthAvailable": true,
                    "stateAvailable": true
                }
            ]
        }
    }
}
```
### Example Error

```json
{
  "id" : 22,
  "jsonrpc" : "2.0",
  "error" :
  {
    "code" : 22,
    "message" : "During API call the unknown error has occurred",
    "data" :
    {
      "method" : "RC.GetCapabilities"
    }
  }
}
```
