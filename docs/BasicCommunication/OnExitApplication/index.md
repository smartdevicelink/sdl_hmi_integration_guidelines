## OnExitApplication

Type
: Notification

Sender
: HMI

Purpose
: Inform SDL that an application must be unregistered or put into the NONE HMI state.

### Notification

#### Parameters

|Name|Type|Mandatory|Additional|Description|
|:---|:---|:--------|:---------|:----------|
|reason|Common.ApplicationToNONEReason|true|||
|appID|Integer|true|||

#### ApplicationToNONEReason

|Name|Value|
|:---|:----|
|DRIVER_DISTRACTION_VIOLATION|0|
|USER_EXIT|1|

### Sequence Diagrams
|||
User Exits Application
![OnExitApplication](./assets/OnExitApplicationUser.png)
|||
|||
Application Not Authorized
![OnExitApplication](./assets/OnExitApplicationUnauth.png)
|||

#### JSON Example Notification
```json
{
	"jsonrpc" : "2.0",
	"method" : "BasicCommunication.OnExitApplication",
	"params" :
	{
		"appID" : 65544,
		"reason" : "USER_EXIT"
	}
}
```
