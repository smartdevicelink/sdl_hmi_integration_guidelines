## OnDeviceStateChanged

Type
: Notification

Sender
: HMI

Purpose
: Inform about BLUETOOTH device state changed

SDL PoliciesManager needs this notification for updating the data in policies database. Information about unpaired device will cause SDL PoliciesManager to remove all data related to it from the database.   


_**HMI must:**_   
Notify SDL when the state of bluetooth paired device has been changed.
   
_**Note:**_   
SDL ignores all invalid notifications which come from HMI (invalid JSON, invalid data types/bounds etc).
Unpairing of the device is NOT a trigger for new PTU sequence.

#### Parameters

|Name|Type|Mandatory|Additional|
|:---|:---|:--------|:---------|
|deviceState|[Common.DeviceState]|true||
|deviceInternalId|String|true|minlength: 0<br>maxlength: 500|
|deviceId|[Common.DeviceInfo]|false||

[Common.DeviceState]: https://github.com/smartdevicelink/sdl_hmi_integration_guidelines/blob/develop/docs/Common/Enums/index.md#devicestate
[Common.DeviceInfo]: https://github.com/smartdevicelink/sdl_hmi_integration_guidelines/blob/develop/docs/Common/Structs/index.md#deviceinfo

#### JSON Example Notification
```
{
	"jsonrpc" : "2.0",
	"method" : "SDL.OnDeviceStateChanged",
	"params" :  
	{
		"deviceInternalId":"0017CAF56A51",
      "deviceState":"UNPAIRED"	}
}
```
