## UpdateTurnList

### Request
#### Parameters
|Name|Type|Mandatory|Additional|Description|
|:---|:---|:--------|:---------|:----------|
|turnList|Common.Turn|false|array: true<br>minsize: 1<br>maxsize: 100||
|softButtons|Common.SoftButton|false|array: true<br>minsize: 0<br>maxsize: 1||
|appID|Integer|true|||
#### Turn
|Name|Type|Mandatory|Additional|Description|
|:---|:---|:--------|:---------|:----------|
|navigationText|Common.TextFieldStruct|false|||
|turnIcon|Common.Image|false|||
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
