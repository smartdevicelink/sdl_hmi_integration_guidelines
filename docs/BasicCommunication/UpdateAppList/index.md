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

!!! Note
Cloud apps will appear in the app list before they are connected and registered. The `cloudConnectionStatus` parameter in [Common.HMIApplication](../../common/structs/#hmiapplication) can be used to track the connection status of the cloud app. The `isCloudApp` parameter can be used by the HMI to differentiate or group cloud apps away from mobile connected SDL applications. 

The connection to the cloud app will be created by Core after the user activates the app via [SDL.ActivateApp](../../SDL/ActivateApp).
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

### JSON Message Examples

#### Example Request

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
      },
      {
        "appName" : "Cloud App",
        "icon" : "tmp/SDL/app/cloud/icon.png",
        "appID" : 65543,
        "cloudConnectionStatus": "NOT_CONNECTED",
        "isCloudApplication": true,
        "deviceInfo": {
          "id": "a3cadf8a",
          "isSDLAllowed": true,
          "name": "ws://192.168.1.1:3000/",
          "transportType": "CLOUD_WEBSOCKET"
        }
      }
    ]
  }
}
```

#### Example Response

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

#### Example Error

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
