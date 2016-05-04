## OnKeyboardInput


### Notification

#### Parameters

|Name|Type|Mandatory|Additional|Description|
|:---|:---|:--------|:---------|:----------|
|event|Common.KeyboardEvent|true|||
|data|String|false|minlength: 0<br>maxlength: 500||

#### KeyboardEvent

|Name|Value|
|:---|:----|
|KEYPRESS|0|
|ENTRY_SUBMITTED|1|
|ENTRY_VOICE|2|
|ENTRY_CANCELLED|3|
|ENTRY_ABORTED|4|

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

#### JSON Example Notification
```json

```
