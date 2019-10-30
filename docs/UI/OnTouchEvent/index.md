## OnTouchEvent

Type
: Notification

Sender
: HMI

Purpose
: Inform SDL that a touch event has occurred in the HMI.

### Notification

#### Parameters

|Name|Type|Mandatory|Additional|
|:---|:---|:--------|:---------|
|type|[Common.TouchType](../../common/enums/#touchtype)|true||
|event|[Common.TouchEvent](../../common/structs/#touchevent)|true|array: true<br>minsize: 1<br>maxsize: 10|


### Sequence Diagrams
|||
OnTouchEvent moving two fingers stop together
![OnTouchEvent](./assets/OnTouchEventTwoFingers.png)
|||
|||
OnTouchEvent moving two fingers one stops first
![OnTouchEvent](./assets/OnTouchEventTwoFingersOneStop.png)
|||

### JSON Example Notification
```json
{
  "jsonrpc" : "2.0",
  "method" : "UI.OnTouchEvent",
  "params" :
  {
    "type" : "START",
      "event" :[
             {
                "id":0,
                "ts":[49013],
                "c":[{"x":323,"y":259}]
              }
            ]
  }
}
```
