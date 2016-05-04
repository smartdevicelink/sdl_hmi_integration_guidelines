## Show


### Request

#### Parameters

|Name|Type|Mandatory|Additional|Description|
|:---|:---|:--------|:---------|:----------|
|showStrings|Common.TextFieldStruct|true|array: true<br>minsize: 0<br>maxsize: 7||
|alignment|Common.TextAlignment|false|||
|graphic|Common.Image|false|||
|secondaryGraphic|Common.Image|false|||
|softButtons|Common.SoftButton|false|array: true<br>minsize: 0<br>maxsize: 8||
|customPresets|String|false|array: true<br>minsize: 0<br>maxsize: 10<br>maxlength: 500||
|appID|Integer|true|||

#### TextFieldStruct

|Name|Type|Mandatory|Additional|Description|
|:---|:---|:--------|:---------|:----------|
|fieldName|Common.TextFieldName|true|||
|fieldText|String|true|maxlength: 500||

#### TextAlignment

|Name|Value|
|:---|:----|
|LEFT_ALIGNED|0|
|RIGHT_ALIGNED|1|
|CENTERED|2|

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
Active App shows and is deactivated then reactivated
![Show](./assets/ShowAppReactivated.png)
|||
|||
Inactive App Sends Show
![Show](./assets/ShowAppInactive.png)
|||
|||
Show with Soft Buttons
![Show](./assets/ShowSoftButtons.png)
|||
|||
Show Text Fields
![Show](./assets/ShowTextFields.png)
|||
