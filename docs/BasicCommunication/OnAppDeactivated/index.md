## OnAppDeactivated

Type
: Notification

Sender
: HMI

Purpose
: Inform the application it is no longer active on the HMI

SDL requires this notification in order to keep the mobile application from sending RPC's related to the HMI's functionality (e.g. adding commands for VR, starting an interaction with the user, speaking text via TTS, etc).


In the event a navigation application is in `FULL` and the HMI sends `OnAppDeactivated`, SDL must set the navigation application to `LIMITED` with the AudioStreamingState set to `AUDIBLE`, VideoStreamingState `STREAMABLE`.

In the event a media projection application is in `FULL` and the HMI sends `OnAppDeactivated` (user goes out from media app screen to HU menu), SDL must set the app to `LIMITED` with the AudioStreamingState set to `AUDIBLE`, VideoStreamingState `STREAMABLE`.  

In the event a non media projection application is in `FULL`  the HMI sends `OnAppDeactivated` (user goes out from media app screen to HU menu), SDL must set the app to `LIMITED` with the AudioStreamingState set to `NOT_AUDIBLE`, VideoStreamingState `STREAMABLE`.

!!! NOTE

The information about the application (name, appID, etc) is provided by SDL via the RPCs `UpdateAppList` or `OnAppRegistered`. SDL ignores all invalid notifications which come from the HMI (invalid JSON, invalid data types/bounds, etc).

!!!

### Notification

#### Parameters

|Name|Type|Mandatory|Additional|
|:---|:---|:--------|:---------|
|appID|Integer|true||

### Sequence Diagrams
|||
User Switches Apps
![OnAppDeactivated](./assets/OnAppDeactivated.png)
|||

#### JSON Example Notification
```json
{
  "jsonrpc" : "2.0",
  "method" : "BasicCommunication.OnAppDeactivated",
  "params" :
  {
    "appID" : 65544,
    "reason" : "PHONECALL"
  }
}
```
