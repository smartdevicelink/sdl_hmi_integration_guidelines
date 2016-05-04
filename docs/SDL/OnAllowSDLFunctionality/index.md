## OnAllowSDLFunctionality


### Notification

#### Parameters

|Name|Type|Mandatory|Additional|Description|
|:---|:---|:--------|:---------|:----------|
|device|Common.DeviceInfo|false|||
|allowed|Boolean|true|||
|source|Common.ConsentSource|true|||

#### DeviceInfo

|Name|Type|Mandatory|Additional|Description|
|:---|:---|:--------|:---------|:----------|
|name|String|true|||
|id|String|true|||
|transportType|Common.TransportType|false|||
|isSDLAllowed|Boolean|false|||

#### ConsentSource

|Name|Value|
|:---|:----|
|GUI|0|
|VUI|1|

#### JSON Example Notification
```json

```
