## OnAppActivated

Type
: Notification

Sender
: HMI

Purpose
: Inform SDL that the user has chosen to activate an application.

SDL requires this notification to know if the user has requested for an application to be in focus and start operating, based on the HMI's functionality.

When `OnAppActivated` is received, SDL sends an `ActivateApp` request to confirm the named application may be activated.

!!! MUST

  1. Send an `OnAppActivated` notification when the user chooses an application on the HMI.
  2. Wait for `ActivateApp` before the HMI can display the application related screen.

!!!

!!! NOTE

`OnAppActivated` shows the user's intent to activate the named application.

`ActivateApp` is a request created by SDL that provides the permission for the application to access the HMI's functionality.

!!!

### Notification

#### Parameters

|Name|Type|Mandatory|Description|
|:---|:---|:--------|:---------|
|appID|Integer|true|ID of the application to be activated on the HMI|


### Sequence Diagrams
|||
User Activates App
![OnAppActivated](./assets/OnAppActivated.png)
|||

#### JSON Example Notification
```json
{
  "jsonrpc" : "2.0",
  "method" : "BasicCommunication.OnAppActivated",
  "params" :
  {
    "appID" : 65544
  }
}
```
