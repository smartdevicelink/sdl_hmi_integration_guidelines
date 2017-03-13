## OnAllowSDLFunctionality
Type : Notification

Sender : HMI

Purpose : Inform about allowing SDL functionality

### Notification
Notifies about user/HMI allowing SDL functionality or disallowing access to all mobile apps on the specified device.

!!! MUST  
Send `OnAllowSDLFuntionality` notification to SDL as a result of user’s choice about device data consent via pop-up dialog or user’s settings change in Settings Menu (if applicable)
!!!

!!! NOTE   
1. SDL ignores all invalid notifications which come from HMI (invalid JSON, invalid data types/bounds etc).   
2. In case SDL PoliciesManager receives _SDL.OnAllowSDLFunctionality_ with _allowed=false_ and without _device_ param from HMI, PoliciesManager must record all of currently registered devices as NOT consented in Local PT.   
3. In case PoliciesManager receives _SDL.OnAllowSDLFunctionality_ with _allowed=true_ and without _device_ param from HMI, PoliciesManager must:   
   - record all of currently registered devices as consented in Local PT;   
   - send _BC.ActivateApp_(params, level: ”default_hmi”-value-from-assigned-policies) to HMI (even if this “default_hmi” value is NONE or BACKGROUND).   
   - notify mobile application via _OnHMIStatus_(params, level: ”default_hmi”-value-from-assigned-policies).   
4. In case PoliciesManager receives _SDL.OnAllowSDLFunctionality_ with _allowed=false_ and with _device_ param, PoliciesManager must record the named device (_device_ param) as NOT consented in Local PT ("user_consent_records" -> _device_ sub-section) and send _BC.ActivateApp_ request with _level_ param of the value from 'default_hmi' key of 'pre-DataConsent'section of Local PT to HMI.   
5. In case PoliciesManager receives _SDL.OnAllowSDLFunctionality_ with _allowed=true_ and with _device_ param from HMI, PoliciesManager must record the named device (_device_ param) as consented in Local PT ("device_data" section `<device_id>` subsection "user_consent_records" -> "device" sub-section).
6. PoliciesManager must store the User's consent for device (data consent) records in "device" subsection of "user_consent_records" subsection of `<device_identifier>` section of "device_data" section in Local PT on getting OnAllowSDLFunctionality from HMI.  
!!!

#### Parameters

|Name|Type|Mandatory|Additional|
|:---|:---|:--------|:---------|
|device|[Common.DeviceInfo]|false||
|allowed|Boolean|true||
|source|[Common.ConsentSource]|true||

[Common.DeviceInfo]: ../../common/structs/#deviceinfo
[Common.ConsentSource]: ../../common/enums/#consentsource

### Sequence Diagrams

Preconditions:   
a) Device is connected to the HU.   
b) App_1 is running on this device and is registered with SDL.   
c) App_1 presents in the list of registered apps on HMI.   

|||
1. The User does NOT consent the device.   
![OnAllowSDLFunctionality] (../ActivateApp/assets/User%20does%20not%20consent%20the%20device1.png)
|||
|||
2. The User consents the device.
![OnAllowSDLFunctionality](../ActivateApp/assets/User%20consents%20the%20device2.png)
|||

#### JSON Example Notification
```
{
	"jsonrpc" : "2.0",
	"method" : "SDL.OnAllowSDLFunctionality",
	"params" :  
	{
		"deviceInfo": 
		{
				"name" : “Mary`s Phone”,
				"id" : 8
		}

		“allowed” : true,
		“source” :”GUI”
	}
}

```
