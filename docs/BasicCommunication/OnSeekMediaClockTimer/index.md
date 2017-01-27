## OnSeekMediaClockTimer
  * Type: notification
  * Sender: HMI
  * Purpose: Callback for the seek media clock timer notification.
  
  
  ### Behavior
 A notification will be provided if the user touches (or seeks) to a particular position on the HMI mediaclock timer. 
 The notification will contain a starttime with the position the user has seeked to.
    
1. If HMI sends to SDL _OnSeekMediaClockTimer_ **valid** and **NOT allowed** by PT notification, _**SDL must**_:   
   - log corresponding error internally;
   - ignore this _OnSeekMediaClockTimer_ notification.   
_**SDL must NOT**_: transfer _OnSeekMediaClockTimer_ notification from HMI to mobile application. 

2. If HMI sends to SDL _OnSeekMediaClockTimer_ **valid** and **allowed** by PT notification, _**SDL must**_:   
   - transfer _OnSeekMediaClockTimer_ notification from HMI to mobile application.

_**Note:**_
SDL must transfer _OnSeekMediaClockTimer_ notification from HMI to mobile app **independently** on value of "enableSeek"
(true or false) parameter at _SetMediaClockTimer_request_.

### Request

#### Parameters

|Name|Type|Mandatory|Additional|
|:---|:---|:--------|:---------|
|seekTime|[Commom.TimeFormat]|true|see [StartTime]|
|appID|Integer|true|The ID of application that relates to this mediaclock position change.|

[Commom.TimeFormat]: https://github.com/smartdevicelink/sdl_hmi_integration_guidelines/blob/develop/docs/Common/Structs/index.md#timeformat
[StartTime]: https://github.com/smartdevicelink/sdl_hmi_integration_guidelines/blob/develop/docs/UI/SetMediaClockTimer/index.md#parameters
### Response

#### Parameters

This RPC has no additional parameter requirements.

### Example Request
```json
```

### Example Response

### Sequence Diagrams
