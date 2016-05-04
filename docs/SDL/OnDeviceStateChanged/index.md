## OnDeviceStateChanged


### Notification

#### Parameters

|Name|Type|Mandatory|Additional|Description|
|:---|:---|:--------|:---------|:----------|
|deviceState|Common.DeviceState|true|||
|deviceInternalId|String|true|minlength: 0<br>maxlength: 500||
|deviceId|Common.DeviceInfo|false|||

#### DeviceState

|Name|Value|
|:---|:----|
|UNKNOWN|0|
|UNPAIRED|1|

#### DeviceInfo

|Name|Type|Mandatory|Additional|Description|
|:---|:---|:--------|:---------|:----------|
|name|String|true|||
|id|String|true|||
|transportType|Common.TransportType|false|||
|isSDLAllowed|Boolean|false|||

#### JSON Example Notification
```json

```
