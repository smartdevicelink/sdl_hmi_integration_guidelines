## UnsubscribeWayPoints

Type
: Function

Sender
: SDL

Purpose
: Unsubscribe from periodic navigation waypoint/destination updates

### Request

!!! MUST
Stop sending waypoint updates to SDL
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
