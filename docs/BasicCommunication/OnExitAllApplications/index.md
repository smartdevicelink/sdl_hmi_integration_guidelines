## OnExitAllApplications


### Notification

#### Parameters

|Name|Type|Mandatory|Additional|Description|
|:---|:---|:--------|:---------|:----------|
|reason|Common.ApplicationsCloseReason|true|||

#### ApplicationsCloseReason

|Name|Value|
|:---|:----|
|IGNITION_OFF|0|
|MASTER_RESET|1|
|FACTORY_DEFAULTS|2|
|SUSPEND|3|

### Sequence Diagrams
#### Exit All Apps on Ignition Off
![OnExitAllApplications](./assets/OnExitAllApps.png)
