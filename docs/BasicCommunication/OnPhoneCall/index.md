## OnPhoneCall

Type
: Notification

Sender
: HMI

Purpose
: Notify SDL that a Phone Call event has started or completed.

!!! NOTE

When SDL receives `OnPhoneCall`(`isActive`:`true`), SDL will change the `HMILevel` of all applications in `FULL` or `LIMITED` to `BACKGROUND`. Once the phone call has ended and the HMI sends `OnPhoneCall`(`isActive`:`false`), SDL will return the applications to their previous `HMILevel`s. SDL does not send [ActivateApp](../activateapp), or [OnResumeAudioSource](../onresumeaudiosource) after the call has ended.

!!!

!!! MUST

  1. Send `OnPhoneCall` with the appropriate `isActive` parameter value on the start and send of a phone call. `isActive`:`true` when the phone call is active. `isActive`:`false` when then phone call has ended.
  2. Internally change the `HMILevel`s of the applications in `FULL` or `LIMITED` once the call as started.
  3. Resume applications to their previous `HMILevel` once the phone call has ended.

!!!


### Notification

#### Parameters

|Name|Type|Mandatory|Additional|
|:---|:---|:--------|:---------|
|isActive|Boolean|true||

### Sequence Diagrams
|||
Phone Call
![OnPhoneCall](./assets/OnPhoneCall.png)
|||

#### JSON Example Notification
```json
{
  "jsonrpc" : "2.0",
  "method" : "BasicCommunication.OnPhoneCall"
     "params" :
  {
       "isActive": true
     }
}
```
