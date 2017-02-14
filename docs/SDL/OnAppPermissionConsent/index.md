## OnAppPermissionConsent


### Notification
Type
: Notification  
Sender
: HMI  
Purpose
: Inform about the User permission changes for some functionality for the named application.

Initiated by HMI for specifying the allowance for the application to perform some functionality.The notification informs Policy Manager about some changes in application permissions, that effect application behavior on HMI.  
**HMI MUST**  
1) send `OnAppPermissionConsent` when User answers to prompt about app's permisstions consent.  
2) send `OnAppPermissionConsent` when User enters settings menu and allows/disallows app's permissions.  
3) use the pair of values id<->name in PermissionItem structure which were obtained via `GetListOfPermissions` response  
4) send `OnAppPermissionConsent` when User changes `ExternalConsentStatus`.


_SDL information:_  
PoliciesManager applies the changes to all applications in case `OnAppPermissionConsent` is received without `<appID>` parameter.
PoliciesManager applies the changes received via `OnAppPermissionConsent` according to its internal rules (update appropriate application permissions sections in the policies database etc).


!!! NOTE  
a) SDL ignores all invalid notifications which come from HMI (invalid JSON, invalid data types/bounds etc).  
b) `ExternalConsentStatus` either user_dissalows or user_allows applications functional groupings depending on predefined settings in policy table.  
c) SDL  uses `OnAppPermissionConsent` value (ON/OFF) received from HMI through ignition cycles until this value is changed by corresponding notification from HMI.

#### Parameters

|Name|Type|Mandatory|Additional|
|:---|:---|:--------|:---------|
|appID|Integer|false||
|consentedFunctions|[Common.PermissionItem]|true|array: true<br>minsize: 1<br>maxsize: 100|
|ExternalConsentStatus|[Common.ExternalConsentStatus]|false|array: true <br>minsize: 1<br>maxsize: 100
|source|[Common.ConsentSource]|true|

[Common.PermissionItem]: https://github.com/smartdevicelink/sdl_hmi_integration_guidelines/blob/develop/docs/Common/Structs/index.md#permissionitem
[Common.ExternalConsentStatus]: https://github.com/smartdevicelink/sdl_hmi_integration_guidelines/blob/develop/docs/Common/Structs/index.md#externalconsentstatus
[Common.ConsentSource]: https://github.com/smartdevicelink/sdl_hmi_integration_guidelines/blob/develop/docs/Common/Enums/index.md#consentsource
### Sequence Diagrams


OnAppPermissionConsent (User answers to prompt about app's permisstions consent)   
![OnAppPermissionConsent](https://github.com/smartdevicelink/sdl_hmi_integration_guidelines/blob/develop/docs/SDL/OnAppPermissionConsent/assets/OnAppPermissionConsent.png)


OnAppPermissionConsent (id<->name dependency)
![OnAppPermissionConsent](https://github.com/smartdevicelink/sdl_hmi_integration_guidelines/blob/develop/docs/SDL/OnAppPermissionConsent/assets/OnAppPermissionConsent2.png)


#### JSON Example Notification
```
{
	"jsonrpc" : "2.0",
	"method" : "SDL.OnAppPermissionConsent",
	"params" :  
	{
    "appID":13759,
    "consentedFunctions":[
     {"allowed":false,
      "id":4734356,
      "name":"DrivingCharacteristics"
     }],
    "source":"GUI"
    }}

```
