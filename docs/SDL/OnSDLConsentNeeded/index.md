## OnSDLConsentNeeded
Type
: Notification

Sender
: SDL

Purpose
: Send from SDL to HMI to notify that data consent is needed for device

The notification is applicable only for the case when the device is not consented by the user and  the user requests Policy Table update from HMI.

_**HMI must:**_ 
1) Initiate the sequence of device data consent on getting OnSDLConsentNeeded.   
2) Upon getting _OnSDLConsentNeeded_, request _SDL.GetUserFriendlyMessages_ from SDL.   
3) Display the 'device consent' dialog after getting _SDL.GetUserFriendlyMessages_response_ from SDL.   
4) Send _OnAllowSDLFunctionality_ (true or false) after and depending on User's choice on HMI.   

For more details see the following diagrams:     
   - [The User does NOT consent the device](https://github.com/DrachenkoAnastasiia/sdl_hmi_integration_guidelines/blob/PTU_external_proprietary/docs/SDL/ActivateApp/assets/User%20does%20not%20consent%20the%20device1.png).   
   - [The User consents the device](https://github.com/DrachenkoAnastasiia/sdl_hmi_integration_guidelines/blob/PTU_external_proprietary/docs/SDL/ActivateApp/assets/User%20consents%20the%20device2.png).

#### Parameters

|Name|Type|Mandatory|Additional|
|:---|:---|:--------|:---------|
|device|[Common.DeviceInfo]|true||

[Common.DeviceInfo]: https://github.com/smartdevicelink/sdl_hmi_integration_guidelines/blob/develop/docs/Common/Structs/index.md#deviceinfo

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
