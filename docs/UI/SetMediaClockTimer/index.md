## SetMediaClockTimer

Type
: Function

Sender
: SDL

Purpose
: Set a value and update mode for the media clock of a media application.

The UI.SetMediaClock timer request indicates either an initial value for the media clock timer for a media application or an update to the value. The request may come in for the application which is not currently active on the HMI.   
_**Note:**_   
_SDL uses the information about:_   
- _mediaClock field_   
- _the format of time value confirmed to be supported by HMI within response to UI.GetCapabilities._   

### Request   

#### HMI must:   
1) perform the update type indicated by the `updateMode` parameter:   
- If the application is not active, the HMI must still store the values to be calculated for later display on the HMI.   
- If the application is active, the updates must begin immediately.   

2) exhibit the following behavior based on the `updateMode` parameter:
  * COUNTUP/COUNTDOWN modes:   
    * Start counting up or down from the requested `startTime` value with a step of 1 second;
    * Continue counting up or down until:
           - The next request of _SetMediaClockTimer_ with appropriate parameters comes;   
           - Zero is reached in the case of COUNTDOWN.   
  * PAUSE mode:   
    * Pause the timer that is counting up or down;   
    * If `startTime` or `endTime` parameters are provided, the values must be updated on the HMI.   
  * CLEAR mode:    
    * Clear `startTime` to 00:00:00 in the case that the `startTime` parameter is not provided in the request, otherwise, `startTime` must be updated with a new value. It is up to HMI to determine the way the media clock timer is cleared: either to remove it from display or to set it to zero.   
    
_**Note:**_   
- SDL will not send this request if the `mediaClock` field is not indicated as supported in [UI.GetCapabilities](../getcapabilities).   
- HMI must remember the mode and the value (continuing to update it in case of COUNTUP / COUNTDOWN) of the media clock timer associated with appID and display the accurate values whenever the appID application is activated after having been deactivated.   
- Initially, the appID together with other application-related information is provided by SDL within one of _UpdateAppList_ and _OnAppRegistered_ RPCs.   

3) Respond with the [result code] correspondingly to the results of this RPC execution.
[result code]: https://github.com/smartdevicelink/sdl_hmi_integration_guidelines/blob/develop/docs/UI/SetMediaClockTimer/index.md#response

#### Parameters

|Name|Type|Mandatory|Additional|
|:---|:---|:--------|:---------|
|startTime|[Common.TimeFormat](../../common/structs/#timeformat)|false||
|endTime|[Common.TimeFormat](../../common/structs/#timeformat)|false||
|updateMode|[Common.ClockUpdateMode](../../common/enums/#clockupdatemode)|true||
|appID|Integer|true||

### Response

#### Parameters

This RPC has no additional parameter requirements

### Sequence Diagrams
|||
SetMediaClockTimer COUNTUP and COUNTDOWN for Full and Background applications
![SetMediaClockTimer](./assets/SetMediaClockTimerUpDownFullBackground.png)
|||
|||
SetMediaClockTimer Pause and Resume for Active Application
![SetMediaClockTimer](./assets/SetMediaClockTimerPauseResumeActive.png)
|||
|||
SetMediaClockTimer COUNTDOWN for a deactivated application
![SetMediaClockTimer](./assets/SetMediaClockTimerDownDeactivate.png)
|||

### Example Request

```json
{
  "id" : 109,
  "jsonrpc" : "2.0",
  "method" : "UI.SetMediaClockTimer",
  "params" :
  {
    "startTime" :
    {
         "hours" : 0,
         "minutes" : 18,
         "seconds" : 17
    },
    "updateMode" : "COUNTUP",
    "appID" : 65146
  }
}
```
### Example Response

```json
{
  "id" : 109,
  "jsonrpc" : "2.0",
  "result" :
  {
    "code" : 0,
    "method" : "UI.SetMediaClockTimer"
  }
}
```

### Example Error

```json
{
  "id" : 109,
  "jsonrpc" : "2.0",
  "error" :
  {
    "code" : 11,
    "message" : "Invalid data",
    "data" :
    {
      "method" : "UI.SetMediaClockTimer"
    }
  }
}
```
