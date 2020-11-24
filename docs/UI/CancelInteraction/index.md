## CancelInteraction

Type
: Function

Sender
: SDL

Purpose
: Close an interaction of the specified type

### Request

#### Parameters

|Name|Type|Mandatory|Description|
|:---|:---|:--------|:---------|
|appID|Integer|true||
|cancelID|Integer|false||
|functionID|Integer|true|Can be any one of AlertID, PerformInteractionID, SliderID, ScrollableMessageID, or SubtleAlertID|

### Response

#### Parameters

This RPC has no additional parameter requirements

### Sequence Diagrams

|||
CancelInteraction for any UI.Alert
![CancelInteraction](./assets/CancelInteractionAnyAlert.png)
|||

|||
CancelInteraction for specific UI.Alert using optional cancelID parameter
![CancelInteraction](./assets/CancelInteractionSpecificAlert.png)
|||

|||
CancelInteraction for specific UI.Alert using mismatched cancelID
![CancelInteraction](./assets/CancelInteractionSpecificAlertWrong.png)
|||

### JSON Message Examples

#### Example Request

```json
{
  "id" : 7408,
  "jsonrpc" : "2.0",
  "method" : "UI.CancelInteraction",
  "params" : {
    "appID" : 190838891,
    "cancelID" : 42,
    "functionID" : 12
  }
}
```

#### Example Response

```json
{
  "id" : 7408,
  "jsonrpc" : "2.0",
  "result" :
  {
    "code" : 0,
    "method" : "UI.CancelInteraction"
  }
}
```

#### Example Error

```json
{
  "id" : 7408,
  "jsonrpc" : "2.0",
  "error" :
  {
    "code" : 4,
    "message" : "Request is ignored, because the intended result is already in effect.",
    "data" : {
      "method" : "UI.CancelInteraction"
    }
  }
}
```
