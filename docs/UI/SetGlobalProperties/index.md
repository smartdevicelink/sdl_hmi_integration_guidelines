## SetGlobalProperties

Type
: Function

Sender
: SDL

Purpose
: Set the UI properties of an application.

### Request

#### Parameters

|Name|Type|Mandatory|Additional|
|:---|:---|:--------|:---------|
|vrHelpTitle|String|false|maxlength: 500|
|vrHelp|[Common.VrHelpItem](../../Common/Structs/index.md#vrhelpitem)|false|array: true<br>minsize: 1<br>maxsize: 100|
|menuTitle|String|false|maxlength: 500|
|menuIcon|[Common.Image](../../Common/Structs/index.md#image)|false||
|keyboardProperties|[Common.KeyboardProperties](../../Common/Structs/index.md#keyboardproperties)|false||
|appID|Integer|true||

### Response

#### Parameters

This RPC has no additional parameter requirements

### Sequence Diagrams
|||
SetGlobalProperties for active app on HMI with VR activation
![SetGlobalProperties](./assets/SetGlobalPropertiesActiveVRActivate.png)
|||

### Example Request

```json
{
  "id" : 116,
  "jsonrpc" : "2.0",
  "method" : "UI.SetGlobalProperties",
  "params" :
  {
    "vrHelpTitle" : "Choose the action",
    "vrHelp" :
    [
        {
         "text" : "Pause",
         "image" :
          [
             "value" : "tmp/SDL/app/Pandora/icon_1067.jpg",
             "imageType" : DYNAMIC
          ],
         "position" : 1
        },
        {
         "text" : "Resume",
         "image" :
          [
             "value" : "tmp/SDL/app/Pandora/icon_1083.jpeg",
             "imageType" : DYNAMIC
          ],
         "position" : 2
        },
        {
         "text" : "Skip",
         "image" :
          [
             "value" : "tmp/SDL/app/Pandora/icon_1013.jpeg",
             "imageType" : DYNAMIC
          ],
         "position" : 3
        },
        {
         "text" : "Bookmark",
         "image" :
          [
             "value" : "tmp/SDL/app/Pandora/icon_1046.jpeg",
             "imageType" : DYNAMIC
          ],
         "position" : 4
        }
    ],
    "appID" : 53880
  }
}
```
### Example Response

```json
{
  "id" : 116,
  "jsonrpc" : "2.0",
  "result" :
  {
    "code" : 0,
    "method" : "UI.SetGlobalProperties"
  }
}
```

### Example Error

```json
{
  "id" : 116,
  "jsonrpc" : "2.0",
  "error" :
  {
    "code" : 11,
    "message" : "Invalid data",
    "data" :
    {
      "method" : "UI.SetGlobalProperties"
    }
  }
}
```
