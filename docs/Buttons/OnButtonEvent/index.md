## OnButtonEvent

Type
: Notification

Sender
: HMI

Purpose
: Inform SDL about the occurrence of a button event.

### Notification

#### Parameters

|Name|Type|Mandatory|Additional|
|:---|:---|:--------|:---------|
|name|[Common.ButtonName](../../common/enums/#buttonname)|true||
|mode|[Common.ButtonEventMode](../../common/enums/#buttoneventmode)|true||
|customButtonID|Integer|false|minvalue: 0<br>maxvalue: 65536|
|appID|Integer|false||

### Sequence Diagrams
|||
OnButtonEvent for CUSTOM_BUTTON pressed and released
![OnButtonEvent](./assets/OnButtonEventPressRelease.png)
|||
|||
OnButtonEvent hardware button pressed and released
![OnButtonEvent](./assets/OnButtonEventHardKeyPressRelease.png)
|||

### JSON Example Notification
```json
{
  "jsonrpc" : "2.0",
  "method" : "Buttons.OnButtonEvent",
  "params" :
  {
    "name" : "OK",
    "mode" : "BUTTONDOWN"
  }
}
```
