## ShowConstantTBT


### Request

#### Parameters

|Name|Type|Mandatory|Additional|Description|
|:---|:---|:--------|:---------|:----------|
|navigationTexts|Common.TextFieldStruct|true|array: true<br>minsize: 0<br>maxsize: 5||
|turnIcon|Common.Image|false|||
|nextTurnIcon|Common.Image|false|||
|distanceToManeuver|Float|true|minvalue: 0<br>maxvalue: 1000000000||
|distanceToManeuverScale|Float|true|minvalue: 0<br>maxvalue: 1000000000||
|maneuverComplete|Boolean|false|||
|softButtons|Common.SoftButton|false|array: true<br>minsize: 0<br>maxsize: 3||
|appID|Integer|true|||

#### TextFieldStruct

|Name|Type|Mandatory|Additional|Description|
|:---|:---|:--------|:---------|:----------|
|fieldName|Common.TextFieldName|true|||
|fieldText|String|true|maxlength: 500||

#### Image

|Name|Type|Mandatory|Additional|Description|
|:---|:---|:--------|:---------|:----------|
|value|String|true|maxlength: 65535||
|imageType|Common.ImageType|true|||

#### Image

|Name|Type|Mandatory|Additional|Description|
|:---|:---|:--------|:---------|:----------|
|value|String|true|maxlength: 65535||
|imageType|Common.ImageType|true|||

#### SoftButton

|Name|Type|Mandatory|Additional|Description|
|:---|:---|:--------|:---------|:----------|
|type|Common.SoftButtonType|true|||
|text|String|false|maxlength: 500||
|image|Common.Image|false|||
|isHighlighted|Boolean|false|||
|softButtonID|Integer|true|minvalue: 0<br>maxvalue: 65535||
|systemAction|Common.SystemAction|true|||

### Response

#### Parameters

This RPC has no additional parameter requirements

### Sequence Diagrams
|||
ShowConstantTBT
![ShowConstantTBT](./assets/ShowConstantTBT.jpg)
|||
