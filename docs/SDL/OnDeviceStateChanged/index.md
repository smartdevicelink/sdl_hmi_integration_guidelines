## OnDeviceStateChanged

Type
: Notification

Sender
: HMI

Purpose
: Inform about BLUETOOTH device state changed

SDL PoliciesManager needs this notification for updating the data in policies database. Information about unpaired device will cause SDL PoliciesManager to remove all data related to it from the database.   


!!! MUST:   
Notify SDL when the state of bluetooth paired device has been changed.
!!!   
!!! NOTE:   
SDL ignores all invalid notifications which come from HMI (invalid JSON, invalid data types/bounds etc).
Unpairing of the device is NOT a trigger for new PTU sequence.
!!!

### Notification

#### Parameters

|Name|Type|Mandatory|Additional|
|:---|:---|:--------|:---------|
|deviceState|[Common.DeviceState](../../common/enums/#devicestate)|true||
|deviceInternalId|String|true|minlength: 0<br>maxlength: 500|
|deviceId|[Common.DeviceInfo](../../common/structs/#deviceinfo)|false||

### JSON Example Notification
```json
{
  "jsonrpc" : "2.0",
  "method" : "SDL.OnDeviceStateChanged",
  "params" :  
  {
    "deviceInternalId":"0017CAF56A51",
    "deviceState":"UNPAIRED"
  }
}
```
