## OnDriverDistraction

Type
: Notification

Sender
: HMI

Purpose
: Inform SDL about changes to the Driver Distraction state.

### Notification

#### Parameters

|Name|Type|Mandatory|Additional|
|:---|:---|:--------|:---------|
|state|[Common.DriverDistractionState](../../common/enums/#driverdistractionstate)|true||

### Sequence Diagrams
|||
OnDriverDistraction
![OnDriverDistraction](./assets/OnDriverDistraction.png)
|||

#### JSON Example Notification
```json
{
  "jsonrpc" : "2.0",
  "method" : "UI.OnDriverDistraction",
  "params" :
  {
    "state" : "DD_ON"
  }
}
```
