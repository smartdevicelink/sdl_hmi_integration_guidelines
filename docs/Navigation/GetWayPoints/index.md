## GetWayPoints

Type
: Function

Sender
: SDL

Purpose
: Request for getting waypoint/destination data.

SDL forwards a request from the mobile application to get waypoint/destination data from the embedded navigation system.

### Request

!!! MUST
1. Accept requests for getting details of active destination and waypoints and provide details in response to the request.
2. Send [UI.OnResetTimeout](../../ui/onresettimeout) to SDL in case HMI needs more time for processing `GetWayPoints` request.
!!!

**SDL Note:** In case HMI does not respond to this request within SDL's default timeout (10s by default, [UI.OnResetTimeout](../../ui/onresettimeout) will reset this), SDL will return `GENERIC_ERROR` code to the corresponding mobile app's request


#### Parameters

|Name|Type|Mandatory|Additional|Description|
|:---|:---|:--------|:---------|:----------|
|wayPointType|[Common.WayPointType](../../common/enums/#waypointtype)|true||To request for either the destination only or for all waypoints including destination|
|appID|Integer|true||ID of the application that concerns this RPC|

### Response

!!! MUST   
1. Wait using a predefined timeout for the navigation system to respond with the full data. The system shall wait for data (resetting the timer as necessary with [UI.OnResetTimeout](../../ui/onresettimeout)) until all waypoints have been received.
2. **If additional requests are received:** While a request for getting waypoints is being processed, if HMI receives another request from the same app then the system shall reject the new request with a response of `IN_USE`.   
3. **If there is no active navigation source:** the system shall provide a response of `UNSUPPORTED_RESOURCE`.   
4. **If the predefined timeout expires** _or_ **the system receives a "time out" notification from the navigation system:** the system shall provide a response of `TIMED_OUT`.
    a) The system shall ignore and discard any data received from the navigation system after the timeout period.
5. If the system receives any kind of failure notification other than "time out" from the navigation system, then the system shall provide a response of `REJECTED`.
6. When the system receives all the data from the navigation system within the timeout period, the system shall send provide a response of `SUCCESS` with the received data.
7. The array of waypoints shall be ordered in this manner:
   a) The destination will be set as the first entry in the array
   b) **If "wayPointType" is "ALL":** The remaining entries will be in order based on the route, with the first waypoint being the second entry in the array, the second waypoint being the third entry, and so on.   
8. If there is no active route set then the system send a response of SUCCESS with no `wayPoints` value.   
!!!

#### Parameters

|Name|Type|Mandatory|Additional|Description|
|:---|:---|:--------|:---------|:----------|
|wayPoints|[Common.LocationDetails](../../common/structs/#locationdetails)|false|array: true<br>minsize: 1<br>maxsize: 10||
|appID|Integer|true||ID of the application|

### Sequence Diagrams
|||
GetWayPoints
![GetWayPoints](./assets/GetWayPoints.png)
|||

### JSON Message Examples

#### Example Request

```json
{
	"id" : 543,
	"jsonrpc" : "2.0",
	"method" : "Navigation.GetWayPoints",
	"params" : 
	{
		"wayPointType" : "ALL",
		"appID" : 26743
	}
}
```

#### Example Response

```json
{
	"id" : 543,
	"jsonrpc" : "2.0",
	"result" :
	{
		"code" : 0,
		"method" : "Navigation.GetWayPoints",
		"wayPoints" :
		[
			{
				"phoneNumber" :  "123-456-7890",
				"addressLines" : "addresstext"
			}
		],
		"appID" : 26743
	}
}
```

#### Example Error

```json
{
	"id" : 543,
	"jsonrpc" : "2.0",
	"error" :
	{
		"code" : 11,
		"message" : "The data sent is invalid",
		"data" :
		{
			"method" : "Navigation.GetWayPoints"
		}
	}
}
```
