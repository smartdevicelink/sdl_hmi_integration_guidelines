## OnFindApplications


### Notification

#### Parameters

|Name|Type|Mandatory|Additional|Description|
|:---|:---|:--------|:---------|:----------|
|deviceInfo|Common.DeviceInfo|false|||

#### DeviceInfo

|Name|Type|Mandatory|Additional|Description|
|:---|:---|:--------|:---------|:----------|
|name|String|true|||
|id|String|true|||
|transportType|Common.TransportType|false|||
|isSDLAllowed|Boolean|false|||

### Sequence Diagrams
|||
User Choice After OnAppRegistered
![OnFindApplications](./assets/OnFindApplications.png)
|||
|||
OnFindApplications after Device Chosen by User
![OnFindApplications](./assets/OnFindApplicationsDeviceChosen.png)
|||
