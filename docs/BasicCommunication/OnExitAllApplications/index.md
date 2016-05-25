## OnExitAllApplications

Type
: Notification

Sender
: HMI

Purpose
: Inform SDL to exit every registered application.

### Notification

#### Parameters

|Name|Type|Mandatory|Additional|
|:---|:---|:--------|:---------|
|reason|[Common.ApplicationsCloseReason](../../Common/Enums/index.md#applicationsclosereason)|true||

### Sequence Diagrams
|||
Exit All Apps on Ignition Off
![OnExitAllApplications](./assets/OnExitAllApps.png)
|||

#### JSON Example Notification
```json
{
  "jsonrpc" : "2.0",
  "method" : "BasicCommunication.OnExitAllApplications",
  "params" :
  {
    "reason" : "IGNITION_OFF"
  }
}
```
