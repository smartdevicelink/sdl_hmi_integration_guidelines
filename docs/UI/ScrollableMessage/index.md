## ScrollableMessage


### Request

#### Parameters

|Name|Type|Mandatory|Additional|Description|
|:---|:---|:--------|:---------|:----------|
|messageText|Common.TextFieldStruct|true|||
|timeout|Integer|true|minvalue: 0<br>maxvalue: 65535||
|softButtons|Common.SoftButton|false|array: true<br>minsize: 0<br>maxsize: 8||
|appID|Integer|true|||

#### TextFieldStruct

|Name|Type|Mandatory|Additional|Description|
|:---|:---|:--------|:---------|:----------|
|fieldName|Common.TextFieldName|true|||
|fieldText|String|true|maxlength: 500||

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
ScrollableMessage scrolled and closed by timeout
![ScrollableMessage](./assets/ScrollableMessageScrollTimeout.png)
|||
|||
ScrollableMessage with soft buttons pressed by user
![ScrollableMessage](./assets/ScrollableMessageSoftButtonPress.png)
|||
|||
ScrollableMessage with STEAL_FOCUS button for background application
![ScrollableMessage](./assets/ScrollableMessageStealFocus.png)
|||
