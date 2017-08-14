## IsReady

Type
: Function

Sender
: SDL

Purpose
: Provide information to SDL about presence of any of remote controllable module and its readiness to cooperate with SDL, invoked at SDL system start up.


### Request

#### Parameters

The request does not have specific parameters.

!!! note

1. SDL sends `RC.IsReady` request after HMI confirms its readiness via `BC.OnReady` notification.
2. If HMI responds with `"available":false`, SDL will not further communicate over RC interface with HMI.
3. If HMI does not respond during SDL's default timeout, SDL will continue to send RPCs over RC interface to HMI.

!!!

### Response

!!! must

1. Check whether RC component is available and ready.
2. Respond correspondingly to results of this check.

!!!

#### Parameters

|Name|Type|Mandatory|Additional|
|:---|:---|:--------|:---------|
|available|Boolean|true|Must be true if vehicle RC modules are present and ready to communicate with SDL.|

### Sequence Diagrams

### Example Request

### Example Response

### Example Error


