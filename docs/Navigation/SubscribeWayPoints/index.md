## SubscribeWayPoints

Type
: Function

Sender
: SDL

Purpose
: Subscribe to periodic navigation waypoint/destination updates

### Request

!!! MUST
Send future waypoint updates to SDL using [Navigation.OnWayPointChange](../onwaypointchange)
!!!

!!! note
SDL restores status of subscription to wayPoints-related data during data resumption during 3 consecutive ignition cycles.
!!!

#### Parameters

This RPC has no additional parameter requirements

### Response

#### Parameters

This RPC has no additional parameter requirements

### Sequence Diagrams

|||
SubscribeWayPoints
![SubscribeWayPoints](./assets/SubscribeWayPoints.png)
|||

|||
SubscribeWayPoints Resumption
![SubscribeWayPoints](./assets/SubscribeWayPoints_Resumption.png)
|||

### JSON Message Examples

#### Example Request

```json
{
  "id" : 47,
  "jsonrpc" : "2.0",
  "method" : "Navigation.SubscribeWayPoints",
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
    "method" : "Navigation.SubscribeWayPoints"
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
    "message" : "Already subscribed to waypoints",
    "data" :
    {
      "method" : "Navigation.SubscribeWayPoints"
    }
  }
}
```
