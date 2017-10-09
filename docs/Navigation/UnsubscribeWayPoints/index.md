## UnsubscribeWayPoints

Type
: Function

Sender
: SDL

Purpose
: To unsubscribe from Waypoints/destinations data

### Behavior

!!! MUST

1. Accept requests for unsubscribing from getting WayPoints and Destination data.  
2. Stop sending notifications of WayPoints and Destination data changes to the app when the request to unsubscribe is received.
3. Responds with UNSUPPORTED_RESOURCE in case navigation interface is not available on HMI.



### Sequence Diagram
|||
UnsubscribeWayPoints
![UnsubscribeWayPoints](./assets/UnsubscribeWayPoints.png)
|||

### Example Request
```json
{
	"id" : 42,
	"jsonrpc" : "2.0",
	"method" : "Navigation.UnsubscribeWayPoints"
}
```
### Example Response
```json
{
	"id" : 42,
	"jsonrpc" : "2.0",
	"result" : 
	{
		"code" : 0,
		"method" : " Navigation.UnsubscribeWayPoints "
	}
}
```

### Example Error

```json
{
	"id" : 42,
	"jsonrpc" : "2.0",
	"error" : 
	{
		"code" : 11,
		"message" : " Invalid json or parameters are out of bounds.",
		"data" : 
		{
			"method" : "Navigation.UnsubscribeWayPoints"
		}
	}
}

```
