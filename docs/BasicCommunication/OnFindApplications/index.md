## OnFindApplications

Type
: Notification

Sender
: HMI

Purpose
: Initiate the search for applications on the named device.

### Notification

#### Parameters

|Name|Type|Mandatory|Additional|
|:---|:---|:--------|:---------|
|deviceInfo|[Common.DeviceInfo](../../Common/Structs/index.md#deviceinfo)|false||

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
