## OnButtonPress

Type
: Notification

Sender
: HMI

Purpose
: Inform SDL about a Button Press

### Notification

#### Parameters

|Name|Type|Mandatory|Additional|
|:---|:---|:--------|:---------|
|name|[Common.ButtonName](../../Common/Enums/index.md#buttonname)|true||
|mode|[Common.ButtonPressMode](../../Common/Enums/index.md#buttonpressmode)|true||
|customButtonID|Integer|false|minvalue: 0<br>maxvalue: 65536|
|appID|Integer|false||

### Sequence Diagrams
|||
OnButtonPress short press for CUSTOM_BUTTON
![OnButtonPress](./assets/OnButtonPressShort.png)
|||
|||
OnButtonPress long press for hard button
![OnButtonPress](./assets/OnButtonPressLongHardKey.png)
|||
|||
OnButtonPress for hard button that only supports short press
![OnButtonPress](./assets/OnButtonPressHardKeyShortOnly.png)
|||

#### JSON Example Notification
```json
{
  "jsonrpc" : "2.0",
  "method" : "Buttons.OnButtonPress",
  "params" :
  {
    "name" : "CUSTOM_BUTTON",
    "mode" : "SHORT",
    "customButtonID" : 564
  }
}
```
