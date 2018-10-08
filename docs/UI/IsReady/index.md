## IsReady

Type
: Function

Sender
: SDL

Purpose
: Request ready state of UI Module

### Request

!!! note

1. SDL sends `UI.IsReady` request after HMI confirms its readiness via `BC.OnReady` notification.
2. If HMI responds with `"available":false`, SDL will not further communicate over UI interface with HMI.
3. If HMI does not respond during SDL's default timeout, SDL will continue to send RPCs over UI interface to HMI.

!!!

#### Parameters

The request does not have specific parameters.

### Response

!!! must

1. Check whether UI component is available and ready.
2. Respond correspondingly to results of this check.

!!!

#### Parameters

|Name|Type|Mandatory|Additional|
|:---|:---|:--------|:---------|
|available|Boolean|true||

### Sequence Diagrams
|||
UI Component Ready
![IsReady](./assets/IsReady.png)
|||

### Example Request

```json
{
  "id" : 8,
  "jsonrpc" : "2.0",
  "method" : "UI.IsReady"
}
```
### Example Response

```json
{
  "id" : 8,
  "jsonrpc" : "2.0",
  "result" :
  {
    "available" : false,
    "code" : 0,
    "method" : "UI.IsReady"
  }
}
```

### Example Error

```json
{
  "id" : 8,
  "jsonrpc" : "2.0",
  "error" :
  {
    "code" : 22,
    "message" : " HMI doesn’t have the information about UI availability or some failure occurred ",
    "data" :
    {
      "method" : "UI.IsReady"
    }
  }
}
```
