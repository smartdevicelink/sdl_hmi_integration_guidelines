## OnAllowSDLFunctionality
Type : Notification

Sender : HMI

Purpose : Inform about allowing SDL functionality

### Notification
Notifies about user/HMI allowing SDL functionality or disallowing access to all mobile apps on the specified device.

**HMI must:**  
Send `OnAllowSDLFuntionality` notification to SDL as a result of user’s choice about device data consent via pop-up dialog or user’s settings change in Settings Menu (if applicable)

#### Parameters

|Name|Type|Mandatory|Additional|
|:---|:---|:--------|:---------|
|device|[Common.DeviceInfo](https://github.com/KhrystynaDubovyk/sdl_hmi_integration_guidelines/blob/user_consent_in_terms_of_policies/docs/Common/Structs/index.md#deviceinfo)|false||
|allowed|Boolean|true||
|source|[Common.ConsentSource](https://github.com/KhrystynaDubovyk/sdl_hmi_integration_guidelines/blob/user_consent_in_terms_of_policies/docs/Common/Enums/index.md#consentsource)|true||

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
