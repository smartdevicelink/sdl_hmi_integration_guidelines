## UnsubscribeWayPoints

Type
: Function

Sender
: SDL

Purpose
: Unsubscribe from periodic navigation waypoint/destination updates

### Request

!!! MUST
1. Stop sending waypoint updates to SDL.
2. Send `BC.OnResetTimeout` notification to SDL for reseting timeout in case HMI needs more time for processing the request.
!!!

#### Parameters

This RPC has no additional parameter requirements

### Response

#### Parameters

This RPC has no additional parameter requirements

### Sequence Diagrams

|||
UnsubscribeWayPoints
![UnsubscribeWayPoints](./assets/UnsubscribeWayPoints.png)
|||

### JSON Message Examples

#### Example Request

```json
{
  "id" : 47,
  "jsonrpc" : "2.0",
  "method" : "Navigation.UnsubscribeWayPoints",
  "params" : {}
}
```

#### Example Response

```json
{
  "id" : 47,
  "jsonrpc" : "2.0",
  "result" :
  {
    "code" : 0,
    "method" : "Navigation.UnsubscribeWayPoints"
  }
}
```

#### Example Error

```json
{
  "id" : 47,
  "jsonrpc" : "2.0",
  "error" :
  {
    "code" : 6,
    "message" : "Not subscribed to waypoints",
    "data" :
    {
      "method" : "Navigation.UnsubscribeWayPoints"
    }
  }
}
```
