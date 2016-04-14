## OnSystemRequest


### Notification

#### Parameters

|Name|Type|Mandatory|Additional|Description|
|:---|:---|:--------|:---------|:----------|
|requestType|Common.RequestType|true|||
|url|String|false|minlength: 1<br>maxlength: 1000||
|fileType|Common.FileType|false|||
|offset|Integer|false|minvalue: 0<br>maxvalue: 100000000000||
|length|Integer|false|minvalue: 0<br>maxvalue: 100000000000||
|timeout|Integer|false|minvalue: 0<br>maxvalue: 2000000000||
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

#### FileType

|Name|Value|
|:---|:----|
|GRAPHIC_BMP|0|
|GRAPHIC_JPEG|1|
|GRAPHIC_PNG|2|
|AUDIO_WAVE|3|
|AUDIO_MP3|4|
|AUDIO_AAC|5|
|BINARY|6|
|JSON|7|
