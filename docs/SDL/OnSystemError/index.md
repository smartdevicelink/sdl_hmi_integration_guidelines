## OnSystemError

Type
: Notification

Sender
: HMI

Purpose
: Send notification to SDL Core about system errors

### Notification

#### Parameters

|Name|Type|Mandatory|Additional|
|:---|:---|:--------|:---------|
|error|[Common.SystemError](../../common/enums/#systemerror)|true||

### JSON Message Examples

#### Example Notification
```json
{
  "jsonrpc": "2.0",
  "method": "SDL.OnSystemError",
  "params": {
    "error": "SYNC_REBOOTED"
  }
}
```
