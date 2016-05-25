## OnButtonSubscription

Type
: Notification

Sender
: SDL

Purpose
: Notify the HMI that the specified application's interest in receiving notifications for a button has changed.

### Notification

#### Parameters

|Name|Type|Mandatory|Additional|
|:---|:---|:--------|:---------|
|name|[Common.ButtonName](../../common/enums/index.md#buttonname)|true||
|isSubscribed|Boolean|true||
|appID|Integer|true||

### Sequence Diagrams
|||
OnButtonSubscription
![OnButtonSubscription](./assets/OnButtonSubscription.png)
|||

#### JSON Example Notification
```json
{
  "jsonrpc" : "2.0",
  "method" : "Buttons.OnButtonSubscription",
  "params" :
  {
    "name" : "SEEKLEFT",
    "isSubscribed" : true,
    "appID" : 564
  }
}
```
