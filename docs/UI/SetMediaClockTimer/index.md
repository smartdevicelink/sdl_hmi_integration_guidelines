## SetMediaClockTimer

### Request
#### Parameters
|Name|Type|Mandatory|Additional|Description|
|:---|:---|:--------|:---------|:----------|
|startTime|Common.TimeFormat|false|||
|endTime|Common.TimeFormat|false|||
|updateMode|Common.ClockUpdateMode|true|||
|appID|Integer|true|||
#### TimeFormat
|Name|Type|Mandatory|Additional|Description|
|:---|:---|:--------|:---------|:----------|
|hours|Integer|true|minvalue: 0<br>maxvalue: 59||
|minutes|Integer|true|minvalue: 0<br>maxvalue: 59||
|seconds|Integer|true|minvalue: 0<br>maxvalue: 59||
#### TimeFormat
|Name|Type|Mandatory|Additional|Description|
|:---|:---|:--------|:---------|:----------|
|hours|Integer|true|minvalue: 0<br>maxvalue: 59||
|minutes|Integer|true|minvalue: 0<br>maxvalue: 59||
|seconds|Integer|true|minvalue: 0<br>maxvalue: 59||
#### ClockUpdateMode
|Name|Value|
|:---|:----|
|COUNTUP|0|
|COUNTDOWN|1|
|PAUSE|2|
|RESUME|3|
|CLEAR|4|
### Response
#### Parameters
This RPC has no additional parameter requirements
