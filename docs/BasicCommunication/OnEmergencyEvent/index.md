## OnEmergencyEvent

Type
: Notification

Sender
: HMI

Purpose
: Inform SDL to change all AUDIBLE apps to NOT_AUDIBLE and back.

This notification is used to disable SDL applications audio functionality in the event of an emergency or possibly when the rear camera is active.

!!! NOTE

When SDL receives `OnEmergencyEvent`(`enabled: true`), SDL changes all applications with an `AudioStreamingState` of `AUDIBLE` to `NOT_AUDIBLE`. SDL will restore the previous audio streaming state after receiving `OnEmergencyEvent`(`enabled: false`).

!!!

!!! MAY

  1. Send OnEmergencyEvent when the rear view camera become active.
  2. Reject  navigation requests since the rear view camera is active.
  3. Govern the rear view camera and how it coexists with SDL.

!!!

### Notification

#### Parameters

|Name|Type|Mandatory|Additional|
|:---|:---|:--------|:---------|
|enabled|Boolean|true||

### Sequence Diagrams
|||
Emergency Event Activated
![OnEmergencyEvent](./assets/OnEmergencyEvent.png)
|||

#### JSON Example Notification
```json
{
  "jsonrpc" : "2.0",
  "method" : "BasicCommunication. OnEmergencyEvent"
     "params" :
  {
        "enabled" : "true"

  }

}
```
