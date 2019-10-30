## UpdateSDL

### Notification

Type
: Function

Sender
: HMI

Purpose
: Update the Policy Table request


### Request
The request notifies PolicyManager about Policy Table Update is requested by User on HMI.   
The below describes the behavior related to EXTERNAL_PROPRIETARY Policy flow only.

!!! MUST   
1)	Send UpdateSDL request to SDL in case the user requests Policy Table update on HMI.   
2)	After UpdateSDL response follow the process of Policy Update according to “result” received.
!!!

!!! NOTE   
According to result sent to HMI in UpdateSDL response, SDL will follow Policy Update process:   
1) UP_TO_DATE – Policy Table is now up to date, but anyway SDL starts a new policy update cycle because of user request (e.i. UpdateSDL).   
2) UPDATING – Policy Update process is now in already progress, anyway when currently active update process will be finished, SDL must start PT Update from the beginning.   
3) UPDATE_NEEDED – Policy Table is not up to date, update process must be started by SDL.   
PoliciesManager must initiate the PT Update sequence (that is, PT Exchange) upon User\`s request delivered to SDL via SDL.UpdateSDL() from HMI and provide a response on a request with current PTU status to HMI.   
_Information_: PROPRIETARY Policy flow -> SDL must change the flag from "UPDATE_NEEDED" to "UPDATING" right after _BC.PolicyUpdate_ with SnapshotPT is sent to HMI.
!!!

#### Parameters
This RPC has no additional parameter requirements.

### Response

#### Parameters

|Name|Type|Mandatory|Description|
|:---|:---|:--------|:---------|
|result|[Common.UpdateResult](../../common/enums/#updateresult)|true|Specify result: no update needed, update was successful/unsuccessful, etc.|

### Sequence Diagrams
|||
UpdateSDL UP_TO_DATE - EXTERNAL_PROPRIETARY Policy Table Update Flow
![UpdateSDL](./assets/UpdateSDL%20UPDATING.jpg)
|||
|||
UpdateSDL UPDATING - EXTERNAL_PROPRIETARY Policy Table Update Flow
![UpdateSDL](./assets/UpdateSDL%20UPDATING.jpg)
|||
|||
UpdateSDL UPDATE_NEEDED - EXTERNAL_PROPRIETARY Policy Table Update Flow
![UpdateSDL](./assets/UpdateSDL%20UPDATE_NEEDED.jpg)
|||
|||
UpdateSDL - PROPRIETARY Policy Table Update Flow
![UpdateSDL](./assets/Proprietary_PTU_flow_.png)
|||

### Example Request

```json
{
	"id" : 543,
	"jsonrpc" : "2.0",
	"method" : "SDL.UpdateSDL"
}
```

### Example Response

```json
{
	"id" : 543,
	"jsonrpc" : "2.0",
	"result" : 
	{
		"result" : "UPDATING",
		"code" : 0,
		"method" : "SDL.UpdateSDL"
	}
}
```

### Example Error

```json
{
	"id" : 543,
	"jsonrpc" : "2.0",
	"error" : 
	{
		"code" : 22,
		"message" : "The unknown error has occurred",
		"data" : 
		{
			"method" : "SDL.UpdateSDL"
		}
	}
}
```
