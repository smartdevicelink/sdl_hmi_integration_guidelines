## SetDisplayLayout

Type
: Function

Sender
: SDL

Purpose
: Set the display template for the specified application's persistent display.

### Request

#### Parameters

|Name|Type|Mandatory|Additional|
|:---|:---|:--------|:---------|
|displayLayout|String|true|maxlength: 500|
|appID|Integer|true||

### Response

#### Parameters

|Name|Type|Mandatory|Additional|
|:---|:---|:--------|:---------|
|displayCapabilities|[Common.DisplayCapabilities](../../Common/Structs/index.md#displaycapabilities)|false||
|buttonCapabilities|[Common.ButtonCapabilities](../../Common/Structs/index.md#buttoncapabilities)|false|array: true<br>minsize: 1<br>maxsize: 100|
|softButtonCapabilities|[Common.SoftButtonCapabilities](../../Common/Structs/index.md#softbuttoncapabilities)|false|array: true<br>minsize: 1<br>maxsize: 100|
|presetBankCapabilities|[Common.PresetBankCapabilities](../../Common/Structs/index.md#presetbankcapabilities)|false||

### Sequence Diagrams
|||
SetDisplayLayout Successful with UI.GetCapabilities
![SetDisplayLayout](./assets/SetDisplayLayoutSuccessGetCapabilities.png)
|||
|||
SetDisplayLayout Invalid Data with UI.GetCapabilities
![SetDisplayLayout](./assets/SetDisplayLayoutInvalidData.png)
|||

### Example Request

```json
{
	"id" : 47,
	"jsonrpc" : "2.0",
	"method" : "UI.SetDisplayLayout",
	"params" :
	{
		"displayLayout" : "NON-MEDIA",
		"appID" : 65638
	}
}
```
### Example Response

```json
{
	"id" : 47,
	"jsonrpc" : "2.0",
	"result" :
	{
		"displayCapabilities" :
		{
				"displayType" : GEN2_8_DMA,
				"textFields" : [mainField1, mainField2, alertText1, alertText2, alertText3, scrollableMessageBody, initialInteractionText, navigationText1, navigationText2, audioPassThruDisplayText1, audioPassThruDisplayText2, notificationText]
				"imageFields" :
				[
					{
					 "name" : "softButtonImage",
					 "imageTypeSupported" : ["GRAPHIC_BMP", 											"GRAPHIC_JPEG", "GRAPHIC_PNG"],
					 "imageResolution" :
						{
						 "resolutionWidth" : 32,
						 "resolutionHeight" : 32
						}
					},

					{
					 "name" : "vrHelpItem",
					 "imageTypeSupported" : ["GRAPHIC_BMP", 											"GRAPHIC_JPEG", "GRAPHIC_PNG"],
					 "imageResolution" :
						{
						 "resolutionWidth" : 32,
						 "resolutionHeight" : 32
						}
					},

					{
					 "name" : "appIcon",
					 "imageTypeSupported" : ["GRAPHIC_BMP", 											"GRAPHIC_JPEG", "GRAPHIC_PNG"],
					 "imageResolution" :
						{
						 "resolutionWidth" : 64,
						 "resolutionHeight" : 64
						}
					},
				],

				"mediaClockFormats" : [CLOCK1, CLOCKTEXT4],
				"imageCapabilities" : [DYNAMIC],
				"graphicSupported" : true,
				"templatesAvailable" : ["DEFAULT", "MEDIA", "NON-MEDIA"],

				"screenParams" :
				{
					"resolution" :
						{
						 "resolutionWidth" : 800,
						 "resolutionHeight" : 480
						},

					"touchEventAvailable" :
						{
						 "pressAvailable" : true,
						 "multiTouchAvailable" : true,
						 "doublePressAvailable" : false
						}
				},
				"numCustomPresetsAvailable" : 8
		},

		"buttonCapabilities" :
		[
			{
				"name" : OK,
				"shortPressAvailable" : true,
				"longPressAvailable" : true,
				"upDownAvailable" : true
			},
			{
				"name" : SEEKLEFT,
				"shortPressAvailable" : true,
				"longPressAvailable" : true,
				"upDownAvailable" : true
			},
			{
				"name" : SEEKRIGHT,
				"shortPressAvailable" : true,
				"longPressAvailable" : true,
				"upDownAvailable" : true
			},
			{
				"name" : TUNEUP,
				"shortPressAvailable" : true,
				"longPressAvailable" : true,
				"upDownAvailable" : true
			},
			{
				"name" : TUNEDOWN,
				"shortPressAvailable" : true,
				"longPressAvailable" : true,
				"upDownAvailable" : true
			},
		],

		"softButtonCapabilities" :
		[
			{
				"shortPressAvailable" : true,
				"longPressAvailable" : true,
				"upDownAvailable" : true,
				"imageSupported" : true
			}
		],

		"presetBankCapabilities" :
		{
			"onScreenPresetsAvailable" : true
		},

		"code" : 0,
		"method" : "UI.SetDisplayLayout"
	}
}
```

### Example Error

```json
{
	"id" : 47,
	"jsonrpc" : "2.0",
	"error" :
	{
		"code" : 6,
		"message" : "Ignored as the requested template is already associated with the named appID",
		"data" :
		{
			"method" : "UI.SetDisplayLayout"
		}
	}
}
```
