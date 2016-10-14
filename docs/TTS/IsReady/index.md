## IsReady

Type
: Function

Sender
: SDL

Purpose
: Request ready state of TTS Module

### Request

!!! note

1. SDL sends `VR.IsReady` request after HMI confirms its readiness via `BC.OnREady` notification.
2. If HMI responds with `"available":false`, SDL will not further communicate over VR interface with HMI.
3. If HMI does not respond during SDL's default timeout, SDL will continue to send RPCs over VR interface to HMI.

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
IsReady
![IsReady](./assets/IsReady.png)
|||

### Example Request

```json
{
  "id" : 45,
  "jsonrpc" : "2.0",
  "method" : "TTS.IsReady"
}
```
### Example Response

```json
{
  "id" : 45,
  "jsonrpc" : "2.0",
  "result" :
  {
    "available" : true,
    "code" : 0,
    "method" : "TTS.IsReady"
  }
}
```

### Example Error

```json
{
  "id" : 45,
  "jsonrpc" : "2.0",
  "error" :
  {
    "code" : 11,
    "message" : "Invalid data",
    "data" :
    {
      "method" : "TTS.IsReady"
    }
  }
}
```
