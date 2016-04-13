## SystemRequest

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
