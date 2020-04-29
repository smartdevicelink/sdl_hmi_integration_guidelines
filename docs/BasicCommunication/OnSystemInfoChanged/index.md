## OnSystemInfoChanged

Type
: Notification

Sender
: HMI

Purpose
: Issued by system to SDL to notify that some system param has changed. Currently applied for Sync Language.

### Notification

#### Parameters

|Name|Type|Mandatory|Additional|
|:---|:---|:--------|:---------|
|language|[Common.Language](../../common/enums/#language)|true||

### JSON Message Examples

#### Example Notification

```json
{
  "jsonrpc": "2.0",
  "method": "BasicCommunication.OnSystemInfoChanged",
  "params": {
    "language": "EN-US"
  }
}
```
