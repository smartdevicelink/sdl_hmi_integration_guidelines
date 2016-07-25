## SetMediaClockTimer

Type
: Function

Sender
: SDL

Purpose
: Set a value and update mode for the media clock of a media application.

The UI.SetMediaClock timer request indicates either an initial value for the media clock timer for a media application or an update to the value. The request may come in for the application which is not currently active on the HMI.

!!! must

The HMI must perform the update type indicated by the `updateMode` parameter. If the application is not active, the HMI must still store the values to be calculated for later display on the HMI. If the application is active, the updates must begin immediately.

The HMI should exhibit the following behavior based on the `updateMode` parameter:

  * COUNTUP/COUNTDOWN: Start counting up or down from the requested startTime value with a step of 1 second
  * Continue counting up or down until
    * The next request of SetMediaClockTimer
    * 0 is reached in the case of COUNTDOWN
  * PAUSE: Pause the timer that is counting up or down. If the `startTime` or `endTime` parameters are provided, update the values on the HMI
  * CLEAR: Clear the startTime to 00:00:00 in the case that the `startTime` parameter is not provided, or update the HMI to reflect the new `startTime`

!!!

!!! note

SDL will not send this request if the `mediaClock` field is not indicated as supported in [UI.GetCapabilities](../getcapabilities)

!!!

### Request

#### Parameters

|Name|Type|Mandatory|Additional|
|:---|:---|:--------|:---------|
|startTime|[Common.TimeFormat](../../common/structs/index.md#timeformat)|false||
|endTime|[Common.TimeFormat](../../common/structs/index.md#timeformat)|false||
|updateMode|[Common.ClockUpdateMode](../../common/enums/index.md#clockupdatemode)|true||
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
