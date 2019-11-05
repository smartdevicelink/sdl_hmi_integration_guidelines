## AddStatisticsInfo

Type
: Notification

Sender
: HMI

Purpose
: Sent by system to record statiscs and error counts. Increases statistics specified by statisticType by one.

### Notification

#### Parameters

|Name|Type|Mandatory|Additional|
|:---|:---|:--------|:---------|
|statisticType|[Common.StatisticsType](../../common/enums/#statisticstype)|true||

### JSON Message Examples

#### Example Notification

```json
{
  "jsonrpc": "2.0",
  "method": "SDL.AddStatisticsInfo",
  "params": {
    "statisticType": "iAPP_BUFFER_FULL"
  }
}
```
