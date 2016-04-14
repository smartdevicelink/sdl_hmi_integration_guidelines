## OnPutFile


### Notification

#### Parameters

|Name|Type|Mandatory|Additional|Description|
|:---|:---|:--------|:---------|:----------|
|offset|Integer|false|minvalue: 0<br>maxvalue: 100000000000||
|length|Integer|false|minvalue: 0<br>maxvalue: 100000000000||
|fileSize|Integer|false|minvalue: 0<br>maxvalue: 100000000000||
|FileName|String|true|maxlength: 255||
|syncFileName|String|true|maxlength: 255||
|fileType|Common.FileType|true|||
|persistentFile|Boolean|false|||

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
