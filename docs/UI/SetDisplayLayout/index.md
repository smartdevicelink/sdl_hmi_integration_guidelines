## SetDisplayLayout

### Request
#### Parameters
|Name|Type|Mandatory|Additional|Description|
|:---|:---|:--------|:---------|:----------|
|displayLayout|String|true|maxlength: 500||
|appID|Integer|true|||
### Response
#### Parameters
|Name|Type|Mandatory|Additional|Description|
|:---|:---|:--------|:---------|:----------|
|displayCapabilities|Common.DisplayCapabilities|false|||
|buttonCapabilities|Common.ButtonCapabilities|false|array: true<br>minsize: 1<br>maxsize: 100||
|softButtonCapabilities|Common.SoftButtonCapabilities|false|array: true<br>minsize: 1<br>maxsize: 100||
|presetBankCapabilities|Common.PresetBankCapabilities|false|||
#### DisplayCapabilities
|Name|Type|Mandatory|Additional|Description|
|:---|:---|:--------|:---------|:----------|
|displayType|Common.DisplayType|true|||
|textFields|Common.TextField|true|array: true<br>minsize: 0<br>maxsize: 100||
|imageFields|Common.ImageField|false|array: true<br>minsize: 1<br>maxsize: 100||
|mediaClockFormats|Common.MediaClockFormat|true|array: true<br>minsize: 0<br>maxsize: 100||
|imageCapabilities|Common.ImageType|false|array: true<br>minsize: 0<br>maxsize: 2||
|graphicSupported|Boolean|true|||
|templatesAvailable|String|true|array: true<br>minsize: 0<br>maxsize: 100<br>maxlength: 100||
|screenParams|Common.ScreenParams|false|||
|numCustomPresetsAvailable|Integer|false|minvalue: 1<br>maxvalue: 100||
#### ButtonCapabilities
|Name|Type|Mandatory|Additional|Description|
|:---|:---|:--------|:---------|:----------|
|name|Common.ButtonName|true|||
|shortPressAvailable|Boolean|true|||
|longPressAvailable|Boolean|true|||
|upDownAvailable|Boolean|true|||
#### SoftButtonCapabilities
|Name|Type|Mandatory|Additional|Description|
|:---|:---|:--------|:---------|:----------|
|shortPressAvailable|Boolean|true|||
|longPressAvailable|Boolean|true|||
|upDownAvailable|Boolean|true|||
|imageSupported|Boolean|true|||
#### PresetBankCapabilities
|Name|Type|Mandatory|Additional|Description|
|:---|:---|:--------|:---------|:----------|
|onScreenPresetsAvailable|Boolean|true|||
