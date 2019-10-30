## OnKeyboardInput

Type
: Notification

Sender
: HMI

Purpose
: Inform SDL that a keyboard event has occurred.

### Notification

#### Parameters

|Name|Type|Mandatory|Additional|
|:---|:---|:--------|:---------|
|event|[Common.KeyboardEvent](../../common/enums/#keyboardevent)|true||
|data|String|false|minlength: 0<br>maxlength: 500|

### Sequence Diagrams
|||
OnKeyboardInput SINGLE_KEYPRESS mode
![OnKeyboardInput](./assets/OnKeyboardInputSingle.png)
|||
|||
OnKeyboardInput QUEUE_KEYPRESSES mode
![OnKeyboardInput](./assets/OnKeyboardInputQueue.png)
|||
|||
OnKeyboardInput RESEND_CURRENT_ENTRY mode
![OnKeyboardInput](./assets/OnKeyboardInputResend.png)
|||
|||
OnKeyboardInput cancelled
![OnKeyboardInput](./assets/OnKeyboardInputCancel.png)
|||
|||
OnKeyboardInput ENTRY_VOICE mode
![OnKeyboardInput](./assets/OnKeyboardInputVoice.png)
|||

### Example Notification
```json
{
  "jsonrpc" : "2.0",
  "method" : "UI.OnKeyboardInput",
  "params" :
  {
    "event" : "ENTRY_CANCELLED"
  }
}
```
