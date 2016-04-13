## AlertManeuver

### Request
#### Parameters
|Name|Type|Mandatory|Additional|Description|
|:---|:---|:--------|:---------|:----------|
|softButtons|Common.SoftButton|false|array: true<br>minsize: 0<br>maxsize: 3||
|appID|Integer|true|||
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
