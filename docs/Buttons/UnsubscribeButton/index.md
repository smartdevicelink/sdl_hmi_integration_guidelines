## UnsubscribeButton

Type
: Function  

Sender
: SDL

Purpose
: Unsubscribe application from a button

### Request

!!! MUST
1. Check whether the named button may be successfully unsubscribed.
2. Delete the requested button name from the internal list of subscribed items.
3. Respond with one of appropriate result codes to SDL.
!!!

!!! NOTE
1. In case HMI does not respond SDL's request to subscribe to a button during SDL default timeout 
and SDL responds GENERIC_ERROR to mobile app 
and then HMI responds that the button has been successfully subscribed, 
then SDL sends `UnsubscribeButton` request to HMI, so that the application and HMI are in sync.
2. When an application disconnects unexpectedly, SDL sends `UnsubscribeButton` request for all button names subscribed only by the application just disconnected.
!!!

#### Parameters

|Name|Type|Mandatory|Additional|
|:---|:---|:--------|:---------|
|appID|Integer|true||
|buttonName|[Common.ButtonName](../../common/enums/#buttonname)|true||

### Response

#### Parameters

This RPC has no additional parameter requirements

### Sequence Diagrams

|||
UnsubscribeButton
![UnsubscribeButton](./assets/UnsubscribeButton.png)
|||

### JSON Message Examples

#### Example Request

```json
{
  "id": 32,
  "jsonrpc": "2.0",
  "method": "Buttons.UnsubscribeButton",
  "params": {
    "appID": 680015438,
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
    "method": "Buttons.UnsubscribeButton"
  }
}
```

#### Example Error

```json
{
  "error": {
    "code": 22,
    "data": {
      "method": "Buttons.UnsubscribeButton"
    },
    "message": "An unknown issue occurred"
  },
  "id": 32,
  "jsonrpc": "2.0"
}
```
