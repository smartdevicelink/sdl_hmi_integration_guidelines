## OnButtonEvent

Type
: Notification

Sender
: HMI

Purpose
: Inform SDL about the occurrence of a button event.

!!! note  
1. OnButtonPress/OnButtonEvent -> If no “appID” -> SDL transfers notification to FULL apps only. 
2. OnButtonPress/OnButtonEvent -> If “appID” is present -> SDL transfers notification to the named app, only if it’s in FULL or LIMITED (and ignores notification for BACKROUND & NONE even if there is “appID”) !!!

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
![OnButtonEventOk](./assets/OnButtonEventOk.png)
#### JSON Example Notification
```json
{
  "jsonrpc" : "2.0",
  "method" : "Buttons.OnButtonEvent",
  "params" :
  {
    "name" : OK,
    "mode" : BUTTONDOWN,
  }
}
```
