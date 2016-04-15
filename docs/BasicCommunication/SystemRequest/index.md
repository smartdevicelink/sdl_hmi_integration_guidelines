## SystemRequest

  * Type: Function
  * Sender: SDL
  * Provide the path to a system file that SDL has received from the mobile application

SDL sends SystemRequest to the HMI when SDL receives the SystemRequest RPC from a mobile application.

### Behavior

!!! must

Notify any relevant modules about the location of the file which was transferred.

!!!

!!! important

If the HMI does not respond to SDL's request within a specified timeout period (default of 10 seconds), SDL will return GENERIC_ERROR to the corresponding mobile apps request.

!!!

!!! note

SDL validates all SystemRequests sent from the mobile app and returns DISALLOWED if the app's system request contains a RequestType that is not allowed via Policies.  SDL sends the list of RequestTypes allowed by Policies via OnAppPermissionChanged, UpdateAppList, or OnSystemRequest RPCs. If the HMI sends OnSystemRequest with a RequestType which is disallowed by the current policy table, SDL will ignore the notification.

!!!

### Request

#### Parameters

|Name|Type|Mandatory|Additional|Description|
|:---|:---|:--------|:---------|:----------|
|requestType|Common.RequestType|true|||
|fileName|String|true|minlength: 1<br>maxlength: 255||
|appID|String|false|minlength: 1<br>maxlength: 50||

#### RequestType

|Name|Value|
|:---|:----|
|HTTP|0|
|FILE_RESUME|1|
|AUTH_REQUEST|2|
|AUTH_CHALLENGE|3|
|AUTH_ACK|4|
|PROPRIETARY|5|
|QUERY_APPS|6|
|LAUNCH_APP|7|
|LOCK_SCREEN_ICON_URL|8|
|TRAFFIC_MESSAGE_CHANNEL|9|
|DRIVER_PROFILE|10|
|VOICE_SEARCH|11|
|NAVIGATION|12|
|PHONE|13|
|CLIMATE|14|
|SETTINGS|15|
|VEHICLE_DIAGNOSTICS|16|
|EMERGENCY|17|
|MEDIA|18|
|FOTA|19|

### Response

#### Parameters

This RPC has no additional parameter requirements

### Example Request
``` json
{
	"id" : 59,
	"jsonrpc" : "2.0",
	"method" : "BasicCommunication.SystemRequest"
	"params" :
	{
		"requestType" : "FILE_RESUME",
		"fileName" : "/tmp/fs/mp/images/ivsu_cache/123.json",
		"appID" : 223
	}
}
```

### Example Response
```json
{
	"id" : 59,
	"jsonrpc" : "2.0",
	"result" :
	{
		"code" : 0,
		"method" : "BasicCommunication.SystemRequest"
	}
}
```

### Example Error
```json
{
	"id" : 59,
	"jsonrpc" : "2.0",
	"error" :
	{
		"code" : 11,
		"message" : "Invalid data",
		"data" :
		{
			"method" : "BasicCommunication.SystemRequest"
		}
	}
}
```

### Sequence Diagrams
#### System Request Workflow
![System Request](./assets/SystemRequestWorkflow.png)
