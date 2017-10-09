## GetWayPoints

Type
: Notification

Sender
: SDL

Purpose
: Request for getting waypoint/destination data.

SDL requests to get waypoint/destination information data sent from the mobile application to the embedded navigation system.

### Request

!!! MUST   
1. Accept requests for getting details of active destination and waypoints and provide details in response to the request.
2. Send OnResetTimeout to SDL in case HMI needs more time for processing GetWayPoints request.
!!!

**SDL Note:** In case HMI does not respond SDL's request during SDL default timeout (10 sec), SDL will return `GENERIC_ERROR` code to the corresponding mobile app's request.


#### Parameters

|Param Name|Type|Mandatory|Additional|Description
|:--------|:-------|:--------|:---------|:------------------------
|appID|Integer|true|-|ID of the application|
|wayPointType|[Common.WayPointType](../../common/enums/#waypointtype)|true|defvalue="ALL"|To request for either the destination only or for all waypoints including destination

### Response

!!! MUST   
1. Order the array of waypoints according to the order of the route with details of the Destination being the first entry in the array, the first waypoint on the route will be set as the second entry in the array, the second waypoint on the route will be set as the third entry in the array and so on.   
2. Reject the new request with a response IN_USE if during processing a request HMI receives another request from the same app.   
3. Respond with REJECTED result code in case HMI is currently busy with a higher-priority event.  
4. Responds with UNSUPPORTED_RESOURCE in case navigation interface is not available on HMI.
  
!!!

#### Parameters

|Param Name|Type|Mandatory|Additional|Description
|:--------|:-------|:--------|:---------|:---------|
|wayPoints|[Common.LocationDetails](../../common/structs/#locationdetails)|false|minsize=1<br>maxsize=10<br>array=true|See LocationDetails|


### Sequence Diagrams
|||
GetWayPoints
![GetWayPoints](./assets/GetWayPoints.png)
|||

### JSON Messages Examples

### Request

```
{
	"id" : 543,
	"jsonrpc" : "2.0",
	"method" : "Navigation.GetWaypoints",
	"params" :
     {
       "wayPointType" : "ALL",
       "appID" : 26743
}

```

### Response

```
{
	"id" : 543,
	"jsonrpc" : "2.0",
	"method" : "Navigation.GetWaypoints",
	"result" :
	{
		"wayPoints" :
		[
			{
				"phoneNumber" :  navigationText1,
				"addressLines" : "addresstext"
			},
		"appID" : 26743
	}
}

```
### Error message

```
{
	"id" : 543,
	"jsonrpc" : "2.0",
	"error" :
	{
		"code" : 11,
		"message" : "The data sent is invalid",
		"data" :
		{
			"method" : "Navigation.GetWaypoints"
		}
	}
}

```
