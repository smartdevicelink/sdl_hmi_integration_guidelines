## UpdateSDL

### Notification

Type : Function

Sender : HMI

Purpose : Update the Policy Table request


### Request
The request notifies PolicyManager about Policy Table Update is requested by User on HMI.

**HMI must:**   
1)	Send UpdateSDL request to SDL in case the user requests Policy Table update on HMI.   
2)	After UpdateSDL response follow the process of Policy Update according to “result” received.

_**Note:**_   
According to result sent to HMI in UpdateSDL response, SDL will follow Policy Update process:   
1) UP_TO_DATE – Policy Table is now up to date, but anyway SDL starts a new policy update cycle because of user request (e.i. UpdateSDL).   
2) UPDATING – Policy Update process is now in already progress, anyway when currently active update process will be finished, SDL must start PT Update from the beginning.   
3) UPDATE_NEEDED – Policy Table is not up to date, update process must be started by SDL.   
PoliciesManager must initiate the PT Update sequence (that is, PT Exchange) upon User\`s request delivered to SDL via SDL.UpdateSDL() from HMI and provide a response on a request with current PTU status to HMI.

#### Parameters
This RPC has no additional parameter requirements.

### Response

#### Parameters

|Name|Type|Mandatory|Description|
|:---|:---|:--------|:---------|
|result|Common.UpdateResult|true|Specify result: no update needed, update was successful/unsuccessful, etc.|

[Common.UpdateResult]: https://github.com/smartdevicelink/sdl_hmi_integration_guidelines/blob/develop/docs/Common/Enums/index.md#updateresult

### Sequence Diagrams

UpdateSDL UP_TO_DATE
![UpdateSDL](https://github.com/DrachenkoAnastasiia/sdl_hmi_integration_guidelines/blob/PTU_external_proprietary/docs/SDL/UpdateSDL/assets/UpdateSDL%20UPDATING.jpg)

UpdateSDL UPDATING
![UpdateSDL](https://github.com/DrachenkoAnastasiia/sdl_hmi_integration_guidelines/blob/PTU_external_proprietary/docs/SDL/UpdateSDL/assets/UpdateSDL%20UPDATING.jpg)

UpdateSDL UPDATE_NEEDED
![UpdateSDL] (https://github.com/DrachenkoAnastasiia/sdl_hmi_integration_guidelines/blob/PTU_external_proprietary/docs/SDL/UpdateSDL/assets/UpdateSDL%20UPDATE_NEEDED.jpg)



### Example Request

```
{
	"id" : 543,
	"jsonrpc" : "2.0",
	"method" : "SDL.UpdateSDL"
}
```

### Example Response

```
{
	"id" : 543,
	"jsonrpc" : "2.0",
	"result" : 
	{
		“result” : “UPDATING”
		"code" : 0,
		"method" : "SDL.UpdateSDL"
	}
}
```

### Example Error

```
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
