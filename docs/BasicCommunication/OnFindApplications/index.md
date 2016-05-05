## OnFindApplications

Type
: Notification

Sender
: HMI

Purpose
: Initiate the search for applications on the named device.

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

#### JSON Example Notification
```json
{
	"jsonrpc" : "2.0",
	"method" : "BasicCommunication.OnFindApplications",
	"params" :
	{
		"deviceinfo" :
			{
				"name" : "XT910",
				"id" : 4
			}
	}
}
```
