## PerformInteraction

### Request
#### Parameters
|Name|Type|Mandatory|Additional|Description|
|:---|:---|:--------|:---------|:----------|
|initialText|Common.TextFieldStruct|false|||
|choiceSet|Common.Choice|false|array: true<br>minsize: 1<br>maxsize: 100||
|vrHelpTitle|String|false|maxlength: 500||
|vrHelp|Common.VrHelpItem|false|array: true<br>minsize: 1<br>maxsize: 100||
|timeout|Integer|true|minvalue: 5000<br>maxvalue: 100000||
|interactionLayout|Common.LayoutMode|false|||
|appID|Integer|true|||
#### TextFieldStruct
|Name|Type|Mandatory|Additional|Description|
|:---|:---|:--------|:---------|:----------|
|fieldName|Common.TextFieldName|true|||
|fieldText|String|true|maxlength: 500||
#### Choice
|Name|Type|Mandatory|Additional|Description|
|:---|:---|:--------|:---------|:----------|
|choiceID|Integer|true|minvalue: 0<br>maxvalue: 65535||
|menuName|String|false|maxlength: 500||
|image|Common.Image|false|||
|secondaryText|String|false|maxlength: 500||
|tertiaryText|String|false|maxlength: 500||
|secondaryImage|Image|false|||
#### VrHelpItem
|Name|Type|Mandatory|Additional|Description|
|:---|:---|:--------|:---------|:----------|
|text|String|true|maxlength: 500||
|image|Common.Image|false|||
|position|Integer|true|minvalue: 1<br>maxvalue: 100||
#### LayoutMode
|Name|Value|
|:---|:----|
|ICON_ONLY|0|
|ICON_WITH_SEARCH|1|
|LIST_ONLY|2|
|LIST_WITH_SEARCH|3|
|KEYBOARD|4|
### Response
#### Parameters
|Name|Type|Mandatory|Additional|Description|
|:---|:---|:--------|:---------|:----------|
|choiceID|Integer|false|minvalue: 0<br>maxvalue: 2000000000||
|manualTextEntry|String|false|minlength: 0<br>maxlength: 500||
