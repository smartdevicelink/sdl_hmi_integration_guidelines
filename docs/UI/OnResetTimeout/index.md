## OnResetTimeout

Type
: Notification

Sender
: HMI

Purpose
: Inform SDL that a timeout has been reset via user action for some transient UI element.

### Notification

#### Parameters

|Name|Type|Mandatory|Additional|
|:---|:---|:--------|:---------|
|appID|Integer|true||
|methodName|String|true||

### Sequence Diagrams
|||
OnResetTimeout during PerformInteraction
![OnResetTimeout](./assets/OnResetTimeoutPerformInteraction.png)
|||
|||
OnResetTimeout during ScrollableMessage
![OnResetTimeout](./assets/OnResetTimeoutScrollableMessage.png)
|||
|||
OnResetTimeout KEEP_CONTEXT during alert
![OnResetTimeout](./assets/OnResetTimeoutKeepContextAlert.png)
|||

#### JSON Example Notification
```json
{
	"jsonrpc" : "2.0",
	"method" : "UI.OnResetTimeout",
}
```
