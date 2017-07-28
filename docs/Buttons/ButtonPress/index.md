## ButtonPress

Type
: Function

Sender
: SDL

Purpose
: Emulate button press event on HMI for the common climate or radio control buttons in vehicle

ButtonPress represents a request from an application to change settings of requested RC module by pressing the appropriate button.
This RPC can be sent to the HMI from an application that is registered with REMOTE_CONTROL appHMIType and in one of the following states: FULL, LIMITTED, BACKGROUND.
Module signed by the application in such reques has to be available on HMI and allowed for control change settings.
The system shall list all available RC radio buttons and RC climate buttons in the existing ButtonCapabilities list.

!!! must

  1. Modules sent by application must be available on HMI
  2. Access to control module settings is defined by access mode entered by user on HMI
  3. Requested control buttons have to be available for such module on HMI


!!!

### Request

#### Parameters

|Name|Type|Mandatory|Additional|Description|
|:---|:---|:--------|:---------|:---------|
|moduleType|[Common.ModuleType](https://github.com/OlesiaV/sdl_hmi_integration_guidelines/blob/a118768fa9c6631e168f932919687196bd281f46/docs/Common/Enums/index.md)|true||The module where the button should be pressed|
|buttonName|[Common.ButtonName](https://github.com/smartdevicelink/sdl_hmi_integration_guidelines/blob/SDL_RC_baseline_part2/docs/Common/Enums/index.md)|true|||
|buttonPressMode|[Common.ButtonPressMode](https://github.com/smartdevicelink/sdl_hmi_integration_guidelines/blob/SDL_RC_baseline_part2/docs/Common/Enums/index.md)|true||Indicates whether this is a LONG or SHORT button press event.|
|appID|Integer|true||Internal SDL-assigned ID of the related application|

### Response

#### Parameters

This RPC has no additional parameter requirements

### Sequence Diagrams

|||
ButtonPress
![ButtonPress](https://github.com/smartdevicelink/sdl_hmi_integration_guidelines/blob/SDL_RC_baseline_part2/docs/Buttons/ButtonPress/accessories/ButtonPress.png)
|||

### Example Request

```json
{
    "id": 32,
    "jsonrpc": "2.0",
    "method": "Buttons.ButtonPress",
    "params": {
        "appID": 680015438,
        "buttonName": "VOLUME_UP",
        "buttonPressMode": "LONG",
        "moduleType": "RADIO"
    }
}
```
### Example Response

```json
{
    "id": 32,
    "jsonrpc": "2.0",
    "result": {
        "code": 0,
        "method": "Buttons.ButtonPress"
    }
}
```

### Example Error

```json
{
  "id" : 32,
  "jsonrpc" : "2.0",
  "error" :
  {
    "code" : 22,
    "message" : "An unknown issue occurred ",
    "data" :
    {
      "method" : "Buttons.ButtonPress"
    }
  }
}
```
