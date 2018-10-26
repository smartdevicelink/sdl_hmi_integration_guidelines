## SetMediaClockTimer

Type
: Function

Sender
: SDL

Purpose
: Set a value and update mode for the media clock of a media application.

The UI.SetMediaClock timer request indicates either an initial value for the media clock timer for a media application or an update to this value. The request may come for the application which is not currently active on the HMI.

### Request   

!!! MUST
1. perform the update type indicated by the `updateMode` parameter:   
    * If the application is not active, the HMI must still store the values to be calculated for later display on the HMI.   
    * If the application is active, the updates must begin immediately.   
2. exhibit the following behavior based on the `updateMode` parameter:
    * COUNTUP/COUNTDOWN modes:   
        * Start counting up or down from the requested `startTime` value with a step of 1 second;
        * Continue counting up or down until:
            * The next request of _SetMediaClockTimer_ with appropriate parameters comes;   
            * Zero is reached in the case of COUNTDOWN.   
    * PAUSE mode:   
        * Pause the timer that is counting up or down;   
        * If `startTime` or `endTime` parameters are provided, the values must be updated on the HMI.   
    * CLEAR mode:    
        * Clear `startTime` to 00:00:00 in the case that the `startTime` parameter is not provided in the request, otherwise, `startTime` must be updated with a new value. It is up to HMI to determine the way the media clock timer is cleared: either to remove it from display or to set it to zero.   
3. Respond with the [result code](../setmediaclocktimer/#response) correspondingly to the results of this RPC execution.
!!!
    
!!! NOTE
1) SDL will not send this request if the `mediaClock` field is not indicated as supported in [UI.GetCapabilities](../getcapabilities).   
2) HMI must remember the mode and the value (continuing to update it in case of COUNTUP / COUNTDOWN) of the media clock timer associated with appID and display the accurate values whenever the appID application is activated after having been deactivated.   
3) Initially, the appID together with other application-related information is provided by SDL within one of _UpdateAppList_ and _OnAppRegistered_ RPCs.   
!!!



#### Parameters

|Name|Type|Mandatory|Description|
|:---|:---|:--------|:---------|
|startTime|[Common.TimeFormat]|false|_startTime_ must be provided together with modes: "COUNTUP", "COUNTDOWN", "PAUSE" to HMI. _startTime_ will be ignored for "RESUME", and "CLEAR".|
|endTime|[Common.TimeFormat]|false|endTime can be provided together with modes: "COUNTUP", "COUNTDOWN", "PAUSE" to HMI. To be used to calculate any visual progress bar (if not provided, this feature is ignored). If endTime is greater then startTime for COUNTDOWN or less than startTime for COUNTUP, then the request will return an INVALID_DATA. _endTime_ will be ignored for "PAUSE", "RESUME", and "CLEAR".|
|updateMode|[Common.ClockUpdateMode]|true|Enumeration to control the media clock. In case of pause, resume, or clear, the start time value is ignored and shall be left out. For resume, the time continues with the same value as it was when paused.|
|audioStreamingIndicator|[Common.AudioStreamingIndicator]|false|Indicates that a button press of the Play/Pause button would play, pause or stop the current playback.|
|appID|Integer|true||

[Common.TimeFormat]: ../../common/structs/#timeformat
[Common.ClockUpdateMode]: ../../common/enums/#clockupdatemode
[Common.AudioStreamingIndicator]: ../../common/enums/#audiostreamingindicator

### Response

#### Parameters

|Result|Description|Message type WebSocket|Message type D-Bus|Message Params|Notes|
|:-----|:----------|:---------------------|:-----------------|:-----------|:----|
|Success|SUCCESS: 1. HMI has started counting up or down the media clock from the requested value (in case of COUNTUP or COUNTDOWN requested mode).<br>2. HMI has paused the media clock value (PAUSE requested mode).<br>3. HMI has resumed the media clock in the mode that had been in effect before pausing, i.e. has started counting up or down (RESUME requested mode).<br>4. HMI has cleared the existing media clock value (CLEAR requested mode).|JSON response|Method return|code: 0|HMI must respond right after the action requested with updateMode parameter has been performed.|
|Failure|IGNORED: 1. Request with RESUME mode arrives when the media clock is counting, already resumed or cleared with the previous request.<br>2. Request with PAUSE mode arrives when the media clock is paused or cleared with the previous request.|JSON error message|Method return|code: 6|Applicable to this RPC result codes.|
|Failure|INVALID_DATA: The data sent is invalid (invalid JSON syntax or parameters out of bounds or of wrong type)|JSON error message|Method return|code: 11|Applicable to this RPC result codes.|
|Failure|INVALID_ID: appID is invalid (e.g. doesn’t exist)|JSON error message|Method return|code: 13|Applicable to this RPC result codes.|
|Failure|GENERIC_ERROR: The unknown issue occurred or other codes are not applicable.|JSON error message|Method return|code: 22|Applicable to this RPC result codes.|


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
    "audioStreamingIndicator" : "PAUSE",
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
