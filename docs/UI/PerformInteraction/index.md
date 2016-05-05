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

### Sequence Diagrams
|||
PerformInteraction Successful with VR Only
![PerformInteraction](./assets/PerformInteractionVROnly.png)
|||
|||
PerformInteraction Successful with Manual Only
![PerformInteraction](./assets/PerformInteractionManualOnly.png)
|||
|||
PerformInteraction Timeout with Both
![PerformInteraction](./assets/PerformInteractionBothTimeout.png)
|||

### Example Request

```json
{
	"id" : 79,
	"jsonrpc" : "2.0",
	"method" : "UI.PerformInteraction",
	"params" :
	{
		"initialText" :
		{
				 "fieldName" : initialInteractionText,
				 "fieldText" : "Choose the station:"
		},

		"choiceSet" :
		[
			{
				 "choiceID" : 2415,
				 "menuName" : "Sky.FM"
			},

			{
				 "choiceID" : 2416,
				 "menuName" : "Paradise"
			},

			{
				 "choiceID" : 2417,
				 "menuName" : "100 XR"
			}
		],

		"vrHelp" :
		[
				{
				 "text" : "Sky FM",
				 "image" :
					[
				 		"value" : "tmp/SDL/app/Pandora/icon_5410.jpg",
				 		"imageType" : DYNAMIC
					],

				 "position" : 1
				},

				{
				 "text" : "Paradise",
				 "image" :
					[
				 		"value" : "tmp/SDL/app/Pandora/icon_5423.jpeg",
				 		"imageType" : DYNAMIC
					],
				 "position" : 2
				},

				{
				 "text" : "100 XR",
				 "image" :
					[
				 		"value" : "tmp/SDL/app/Pandora/icon_5465.jpeg",
				 		"imageType" : DYNAMIC
					],
				 "position" : 3
				}
		],

		"timeout" : 15000,
		"appID" : 6493
	}
}
```
### Example Response

```json
{
	"id" : 79,
	"jsonrpc" : "2.0",
	"result" :
	{
		"choiceID" : 2416
		"code" : 0,
		"method" : "UI.PerformInteraction"
	}
}
```

### Example Error

```json
{
	"id" : 79,
	"jsonrpc" : "2.0",
	"error" :
	{
		"code" : 10,
		"message" : "Overlay reached the maximum timeout and closed",
		"data" :
		{
			"method" : "UI.PerformInteraction"
		}
	}
}
```
