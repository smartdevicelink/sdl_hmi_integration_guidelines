## OnTouchEvent


### Notification

#### Parameters

|Name|Type|Mandatory|Additional|Description|
|:---|:---|:--------|:---------|:----------|
|type|Common.TouchType|true|||
|event|Common.TouchEvent|true|array: true<br>minsize: 1<br>maxsize: 10||

#### TouchType

|Name|Value|
|:---|:----|
|BEGIN|0|
|MOVE|1|
|END|2|

#### TouchEvent

|Name|Type|Mandatory|Additional|Description|
|:---|:---|:--------|:---------|:----------|
|id|Integer|true|minvalue: 0<br>maxvalue: 9||
|ts|Integer|true|array: true<br>minsize: 1<br>maxsize: 1000<br>minvalue: 0<br>maxvalue: 2147483647||
|c|Common.TouchCoord|true|array: true<br>minsize: 1<br>maxsize: 1000||

### Sequence Diagrams
|||
OnTouchEvent moving two fingers stop together
![OnTouchEvent](./assets/OnTouchEventTwoFingers.png)
|||
|||
OnTouchEvent moving two fingers one stops first
![OnTouchEvent](./assets/OnTouchEventTwoFingersOneStop.png)
|||
