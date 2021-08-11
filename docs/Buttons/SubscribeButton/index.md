## SubscribeButton

Type
: Function  

Sender
: SDL

Purpose
: Subscribe application to a particular button

### Request
SDL requests HMI to subscribe an application to a `buttonName`.

The request may come for the application being whatever active or in background on HMI (depends on SDL Policy Manager permissions).

During Resumption SDL should restore all button subscriptions for application and send required `SubscribeButton` requests to HMI.

#### Parameters

|Name|Type|Mandatory|Additional|
|:---|:---|:--------|:---------|
|appID|Integer|true||
|buttonName|[Common.ButtonName](../../common/enums/#buttonname)|true||

### Response

!!! MUST
1. Check whether the button subscription can be performed for requested `buttonName`.
2. Respond to SDL within DefaultTimeout period after successful button subscription.
!!!

#### Parameters
This RPC has no additional parameter requirements.

### Sequence Diagrams

|||
[SubscribeButton](./assets/SubscribeButton.png)
|||

### JSON Message Examples

#### Example Request

```json
{
  "id": 32,
  "jsonrpc": "2.0",
  "method": "Buttons.SubscribeButton",
  "params": {
    "appID": "680015438",
    "buttonName": "VOLUME_UP"
  }
}
```

#### Example Response

```json
{
  "id": 32,
  "jsonrpc": "2.0",
  "result": {
    "code": 0,
    "method": "Buttons.SubscribeButton"
  }
}
```

#### Example Error

```json
{
  "error": {
    "code": 22,
    "data": {
      "method": "Buttons.SubscribeButton"
    },
    "message": "An unknown issue occurred"
  },
  "id": 32,
  "jsonrpc": "2.0"
}
```
