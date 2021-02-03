## GetCapabilities

Type
: Function

Sender
: SDL

Purpose
: Inform SDL of the UI capabilities of the vehicle.

### Request

#### Parameters

This RPC has no additional parameter requirements

### Response

#### Parameters

|Name|Type|Mandatory|Additional|
|:---|:---|:--------|:---------|
|displayCapabilities|[Common.DisplayCapabilities](../../common/structs/#displaycapabilities)|true||
|audioPassThruCapabilities|[Common.AudioPassThruCapabilities](../../common/structs/#audiopassthrucapabilities)|true||
|audioPassThruCapabilitiesList|[Common.AudioPassThruCapabilities](../../common/structs/#audiopassthrucapabilities)|false|array: true<br>minsize: 1<br>maxsize: 100|
|hmiZoneCapabilities|[Common.HmiZoneCapabilities](../../common/enums/#hmizonecapabilities)|true||
|softButtonCapabilities|[Common.SoftButtonCapabilities](../../common/structs/#softbuttoncapabilities)|false|array: true<br>minsize: 1<br>maxsize: 100|
|hmiCapabilities|[Common.HMICapabilities](../../common/structs/#hmicapabilities)|false||
|systemCapabilities|[Common.SystemCapabilities](../../common/structs/#systemcapabilities)|false||
|pcmStreamCapabilities|[Common.AudioPassThruCapabilities](../../common/structs/#audiopassthrucapabilities)|false||

### Sequence Diagrams

|||
GetCapabilities  
![GetCapabilities](./assets/GetCapabilities.png)
|||

### JSON Message Examples

#### Example Request

```json
{
  "id" : 18,
  "jsonrpc" : "2.0",
  "method" : "UI.GetCapabilities"
}
```

#### Example Response

```json
{
    "jsonrpc":"2.0",
    "id":42,
    "result":{
        "code":0,
        "method":"UI.GetCapabilities",
        "displayCapabilities":{
            "displayType":"GEN2_8_DMA",
            "displayName":"SDL_HMI",
            "textFields":[
                {
                    "name":"mainField1",
                    "characterSet":"UTF_8",
                    "width":500,
                    "rows":1
                },
                ...
                {
                    "name":"mediaClock",
                    "characterSet":"UTF_8",
                    "width":500,
                    "rows":1
                },
                {
                    "name":"mediaTrack",
                    "characterSet":"UTF_8",
                    "width":500,
                    "rows":1
                },
                {
                    "name":"templateTitle",
                    "characterSet":"UTF_8",
                    "width":100,
                    "rows":1
                },
                {
                    "name":"alertText1",
                    "characterSet":"UTF_8",
                    "width":500,
                    "rows":1
                },
                ...
            ],
            "imageFields":[
                {
                    "name":"softButtonImage",
                    "imageTypeSupported":[
                        "GRAPHIC_BMP",
                        "GRAPHIC_JPEG",
                        "GRAPHIC_PNG"
                    ],
                    "imageResolution":{
                        "resolutionWidth":64,
                        "resolutionHeight":64
                    }
                },
                {
                    "name":"choiceImage",
                    "imageTypeSupported":[
                        "GRAPHIC_BMP",
                        "GRAPHIC_JPEG",
                        "GRAPHIC_PNG"
                    ],
                    "imageResolution":{
                        "resolutionWidth":64,
                        "resolutionHeight":64
                    }
                },
                ...
            ],
            "mediaClockFormats":[
                "CLOCK1",
                "CLOCK2",
                "CLOCK3",
                "CLOCKTEXT1",
                "CLOCKTEXT2",
                "CLOCKTEXT3",
                "CLOCKTEXT4"
            ],
            "graphicSupported":true,
            "imageCapabilities":[
                "DYNAMIC",
                "STATIC"
            ],
            "templatesAvailable":[
                "MEDIA",
                "NON-MEDIA",
                "DEFAULT",
                "NAV_FULLSCREEN_MAP",
                "WEB_VIEW"
            ],
            "screenParams":{
                "resolution":{
                    "resolutionWidth":800,
                    "resolutionHeight":480
                },
                "touchEventAvailable":{
                    "pressAvailable":true,
                    "multiTouchAvailable":true,
                    "doublePressAvailable":false
                }
            },
            "numCustomPresetsAvailable":10
        },
        "systemCapabilities":{
            "videoStreamingCapability":{
                "preferredResolution":{
                    "resolutionWidth":800,
                    "resolutionHeight":380
                },
                "maxBitrate":2147483647,
                "supportedFormats":[
                    {
                        "protocol":"RAW",
                        "codec":"H264"
                    },
                    {
                        "protocol":"RTP",
                        "codec":"H264"
                    },
                    {
                        "protocol":"RTSP",
                        "codec":"Theora"
                    },
                    {
                        "protocol":"RTMP",
                        "codec":"VP8"
                    },
                    {
                        "protocol":"WEBM",
                        "codec":"VP9"
                    }
                ],
                "hapticSpatialDataSupported":true,
                "diagonalScreenSize":8,
                "pixelPerInch":96,
                "scale":1
            },
            "driverDistractionCapability":{
                "menuLength":10,
                "subMenuDepth":2
            }
        },
        "audioPassThruCapabilities":{
            "samplingRate":"44KHZ",
            "bitsPerSample":"8_BIT",
            "audioType":"PCM"
        },
        "audioPassThruCapabilitiesList":[
            {
                "samplingRate":"44KHZ",
                "bitsPerSample":"8_BIT",
                "audioType":"PCM"
            }
        ],
        "pcmStreamCapabilities":{
            "samplingRate":"16KHZ",
            "bitsPerSample":"16_BIT",
            "audioType":"PCM"
        },
        "hmiZoneCapabilities":"FRONT",
        "softButtonCapabilities":[
            {
                "shortPressAvailable":true,
                "longPressAvailable":true,
                "upDownAvailable":true,
                "imageSupported":true
            }
        ],
        "hmiCapabilities":{
            "navigation":true,
            "phoneCall":true
        }
    }
}
```

#### Example Error

```json
{
  "id" : 18,
  "jsonrpc" : "2.0",
  "error" :
  {
    "code" : 22,
    "message" : "During API call the unknown error has occurred",
    "data" :
    {
      "method" : "UI.GetCapabilities"
    }
  }
}
```
