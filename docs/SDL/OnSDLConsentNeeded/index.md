## OnSDLConsentNeeded
Type
: Notification

Sender
: SDL

Purpose
: Send from SDL to HMI to notify that data consent is needed for device

The notification is applicable only for the case when the device is consented by the user and the user requests Policy Table update from HMI.

!!! MUST   
1) Initiate the sequence of device data consent on getting OnSDLConsentNeeded.   
2) Upon getting _OnSDLConsentNeeded_, request _SDL.GetUserFriendlyMessages_ from SDL.   
3) Display the 'device consent' dialog after getting _SDL.GetUserFriendlyMessages_response_ from SDL.   
4) Send _OnAllowSDLFunctionality_ (true or false) after and depending on User's choice on HMI.   
!!!
 
#### Parameters

|Name|Type|Mandatory|Additional|
|:---|:---|:--------|:---------|
|device|[Common.DeviceInfo]|true||

[Common.DeviceInfo]: ../../common/structs/#deviceinfo

### Sequence Diagrams

|||
The User does NOT consent the device
![OnSDLConsentNeeded](./assets/User_does_not_consent_the_device1.png)
|||

|||
The User consents the device
![OnSDLConsentNeeded](./assets/User_consents_the_device2.png)
|||

#### JSON Example Notification
```
{
	"jsonrpc" : "2.0",
	"method" : "SDL.OnSDLConsentNeeded",
	"params" :  
		{
		"deviceInfo" : 
		{
				"name" : “Mary`s Phone”,
				"id" : 8
		}
	}
}
```
