## GetCapabilities


### Request

#### Parameters

|Name|Type|Mandatory|Additional|Description|
|:---|:---|:--------|:---------|:----------|

### Response

#### Parameters

|Name|Type|Mandatory|Additional|Description|
|:---|:---|:--------|:---------|:----------|
|capabilities|Common.ButtonCapabilities|true|array: true<br>minsize: 1<br>maxsize: 100||
|presetBankCapabilities|Common.PresetBankCapabilities|false|||

#### ButtonCapabilities

|Name|Type|Mandatory|Additional|Description|
|:---|:---|:--------|:---------|:----------|
|name|Common.ButtonName|true|||
|shortPressAvailable|Boolean|true|||
|longPressAvailable|Boolean|true|||
|upDownAvailable|Boolean|true|||

#### PresetBankCapabilities

|Name|Type|Mandatory|Additional|Description|
|:---|:---|:--------|:---------|:----------|
|onScreenPresetsAvailable|Boolean|true|||

### Sequence Diagrams
|||
GetCapabilities on system startup
![GetCapabilities](./assets/GetCapabilities.png)
|||
