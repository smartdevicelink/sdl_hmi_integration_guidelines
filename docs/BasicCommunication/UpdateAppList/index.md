## UpdateAppList

Type
: Function

Sender
: SDL

Purpose
: Update HMI's list of registered applications.

SDL may send this request after connecting to a device, and an application successfully registers itself with SDL. This request may also be sent by SDL if the user requests for an update via [OnFindApplications](../onfindapplications).

!!! MUST

  1. Update the list of registered applications.
  2. Use the `appID` provided with this request when sending definite requests or notifications back to a mobile application (e.g. [ActivateApp](../activateapp), [OnCommand](../../ui/oncommand)).
  3. Provide the user with the possibility to choose among a list of registered applications.

!!!

!!! NOTE

SDL adds the VR synonyms of a registered application to the HMI via [OnAppRegistered](../onappregistered).

!!!


### Request

#### Parameters

|Name|Type|Mandatory|Additional|
|:---|:---|:--------|:---------|
|applications|[Common.HMIApplication](../../common/structs/#hmiapplication)|true|array: true<br>minsize: 0<br>maxsize: 100|

### Response

#### Parameters

This RPC has no additional parameter requirements

### Sequence Diagrams
|||
Application Just Registered
![UpdateAppList](./assets/UpdateAppListAppRegister.png)
|||
|||
User Requests Update App List
![UpdateAppList](./assets/UpdateAppListUser.png)
|||

### Example Request

```json
{
  "id" : 75,
  "jsonrpc" : "2.0",
  "method" : "BasicCommunication.UpdateAppList",
  "params" :
  {
    "applications" :
    [
      {
        "appName" : "Beautiful Sound",
        "ngnMediaScreenAppName " : "BeauSo",
        "deviceName" : "Jerry`s Phone",
        "appID" : 65544,
        "hmiDisplayLanguageDesired" : "DE-DE",
        "isMediaApplication" : true
      },

      {
        "appName" : "Go Travel",
        "icon" : "tmp/SDL/app/Go_Travel/icon.png",
        "deviceName" : "XT910",
        "appID" : 65545,
        "hmiDisplayLanguageDesired" : "EN-US",
        "isMediaApplication" : false,
        "appType" : "INFORMATION"
      }
    ]
  }
}
```
### Example Response

```json
{
  "id" : 75,
  "jsonrpc" : "2.0",
  "result" :
  {
    "code" : 0,
    "method" : "BasicCommunication.UpdateAppList"
  }
}
```

### Example Error

```json
{
  "id" : 75,
  "jsonrpc" : "2.0",
  "error" :
  {
    "code" : 22,
    "message" : "During the API call an unknown error has occurred.",
    "data" :
    {
      "method" : "BasicCommunication.UpdateAppList"
    }
  }
}
```
