## OnCommand

Type
: Notification

Sender
: HMI

Purpose
: Inform SDL that a command has been chosen by the User from the UI.

A notification to inform SDL about a command being selected which had previously been added via [UI.AddCommand](../addcommand)

!!! must

The HMI must send the UI.OnCommand notification to SDL when the user selects a command from the application's menu or sub menu.

!!!

### Notification

#### Parameters

|Name|Type|Mandatory|Additional|
|:---|:---|:--------|:---------|
|cmdID|Integer|true|minvalue: 0<br>maxvalue: 2000000000|
|appID|Integer|true||

### Sequence Diagrams
|||
OnCommand
![OnCommand](./assets/OnCommand.png)
|||

### Example Notification
```json
{
  "jsonrpc" : "2.0",
  "method" : "UI.OnCommand",
  "params" :
  {
    "cmdID" : 2318,
     "appID" : 65409
  }
}
```
