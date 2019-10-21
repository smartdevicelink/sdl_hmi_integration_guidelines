# Connecting to SDL
## Requirements to HMI Adapter
WebSocket is the primary means of communicating with the SDL component from the vehicle. In a basic example, an HTML5 HMI would use a native WebSocket library to communicate with SDL Core.

The HMI Adapter must:

!!! must
  * be installed on the same vehicle HU OS where SDL is installed, or the HMI must be able to be networked to SDL and address it via a static IP address.
  * create and initialize components which are defined in the HMI_API specification for the version of SDL which is running on the vehicle HU. (BasicCommunication, UI, Buttons, VR, TTS, Navigation, VehicleInfo, RC, AppService)
  * Establish a separate WebSocket connection with SDL for each of components defined in the HMI_API specification.
  * Use the appropriate corresponding connection when sending responses and notifications to any connected component.

!!!

## Handshake
For opening a WebSocket connection, a handshake must be performed.

!!! info
  1. Client/Server relationship
    * SDL is the Server
    * The HMI is the Client
  2. Host
    * SDL is listening on **127.0.0.1:8087**
  3. WebSocket Protocol Version 13 is used by SDL

!!!

## HMI Component Registration
Once all the requested connections are opened, the HMI must send the JSON request for registering each component.

### Request

Component Registration has the following unique request requirements

| Key     | Value Info    |
| :------------- | :------------- |
| "id"       | a multiple of 100 (100, 200, 300, ..., 700) |
| "jsonrpc" | "2.0" - constant for all messages between SDL and the HMI|
| "method" | "MB.registerComponent" - the request is assigned to SDL's MessageBroker where the component name will be associated with the socket ID. Further, SDL will send messages related to the named component over the corresponding connection|
|"componentName"| The name of the component being registered. Must correspond to the appropriate component name described in the current guidelines.|

### Response

SDL Provides a JSON Response

| Key | Value Info   |
| :------------- | :------------- |
| "id"      | The value from the corresponding request      |
| "result" | Value of id multiplied by 10. HMI can treat this as a successful registration|

### Component Registration Examples

#### Register Component JSON Messages
##### Request
``` json
{
  "id": 700,
  "jsonrpc": "2.0",
  "method": "MB.registerComponent",
  "params": {
    "componentName": "VehicleInfo"
  }
}
```
##### Response
``` json
{
  "id": 700,
  "jsonrpc": "2.0",
  "result": 7000
}
```


#### WebSocket Connection Diagram
|||
Websocket Connection Diagram
![WebSocket Connection Diagram](./assets/WebSocketConnectionDiagram.png)
|||

#### HMI Adapter Initialization
|||
HMI Adapter Init
![HMI Adapter Init](./assets/HMIAdapterInit.png)
|||

# JSON Message Format
This section describes the message structure for communication between your HMI and SDL. The JSON RPC 2.0 format is taken as a basis.

From this point forward the actors for exchanging messages will be considered:
  - **Client** - can send requests and notifications
  - **Server** - can provide responses to requests from a Client and send notifications

## Request
An RPC call is represented by sending a Request object to a Server. The Request object has the following properties

| Property | Description    |
| :------------- | :------------- |
| "id"       | An identifier established by the Client. This value must be of unsigned int type in the frames of communication between your HMI and SDL. The value should never be Null. If "id" is not included the message is assumed to be a notification and the receiver should not respond.|
| "jsonrpc" | A string specifying the version of JSON RPC protocol being used. Must be exactly **"2.0"** currently in all versions of SDL.|
| "method" | A String containing the information of the method to be invoked. The format is `[componentName].[methodName]`.|
| "params" | A structured value that holds the parameter values to be used during the invocation of the method. This property may be omitted.|

### Example Requests
#### Request with No Parameters
```json
{
  "id": 125,
  "jsonrpc": "2.0",
  "method": "Buttons.GetCapabilities"
}
```
#### Request with Parameters
```json
{
  "id": 92,
  "jsonrpc": "2.0",
  "method": "UI.Alert",
  "params": {
    "alertStrings": [
      {
        "fieldName": "alertText1",
        "fieldText": "WARNING"
      },
      {
        "fieldName": "alertText2",
        "fieldText": "Adverse Weather Conditions Ahead"
      }
    ],
    "duration": 4000,
    "softButtons": [
      {
        "type": "TEXT",
        "text": "OK",
        "softButtonID": 697,
        "systemAction": "STEAL_FOCUS"
      }
    ],
    "appID": 8218
  }
}
```

## Notification
A notification is a request object without an `id` property. For all the other properties, see the Request Section above.

The receiver should not reply to a notification, i.e. no response object needs to be returned to the client upon receipt of a notification.

### Example Notifications
#### Notification With No Parameters
```json
{
  "jsonrpc": "2.0",
  "method": "UI.OnReady"
}
```
#### Notifications With Parameters
```json
{
  "jsonrpc": "2.0",
  "method": "BasicCommunication.OnAppActivated",
  "params": {
    "appID": 6578
  }
}

{
  "jsonrpc": "2.0",
  "method": "Buttons.OnButtonPress",
  "params": {
    "mode": "SHORT",
    "name": "OK"
  }
}
```

## Response
On receipt of a request message, the server must reply with a response. The response is expressed as a single JSON Object with the following properties.

| Property | Description    |
| :------------- | :------------- |
| "id"      | Required property which must be the same as the value of the associated request object. If there was an error in detecting the id in the request object, this value must be **null**    |
|"jsonrpc"| Must be exactly **"2.0"**|
|"result"| Required on Success. Must not exist if there was an error invoking the method. The result property must contain a `method` field which is the same as the corresponding request, a `code` field with **0** to indicate success or **21** to indicate success with warnings.  No other [result codes](../common/enums/#result) should be sent in the result property. The result property may also include additional properties as defined in the HMI_API.|

### Example Responses
#### Response with No Parameters
```json
{
  "id": 167,
  "jsonrpc": "2.0",
  "result": {
    "code": 0,
    "method": "UI.Alert"
  }
}
```
#### Response with Parameters
```json
{
  "id": 125,
  "jsonrpc": "2.0",
  "result": {
    "capabilities" : [
      {
        "longPressAvailable" : true,
        "name" : "PRESET_0",
        "shortPressAvailable" : true,
        "upDownAvailable" : true
      },
      {
        "longPressAvailable" : true,
        "name" : "TUNEDOWN",
        "shortPressAvailable" : true,
        "upDownAvailable" : true
      }
    ],
    "presetBankCapabilities": {
      "onScreenPresetsAvailable" : true
    },
    "code" : 0,
    "method" : "Buttons.GetCapabilities"
  }
}
```

## Error Response

!!! must

When an RPC encounters an error, the response object must contain the `error` property instead of the `result` property.

!!!

The error object has the following members:

| Property | Description     |
| :------------- | :------------- |
| "id"       | Required to be the same as the value of "id" in the corresponding Request object. If there was an error in detecting the id of the request object, then this property must be Null   |
| "jsonrpc"| Must be exactly "2.0"|
| "error" | Required on error. Must not exist if there was no error triggered during invocation. The error field must contain a `code` field with the [result code](../common/enums/#result) value that indicates the error type that occurred, a `message` field containing the string that provides a short description of the error, and a `data` field that must contain the `method` from the original request.|

### Examples
#### Response with Error
```json
{
  "id": 103,
  "jsonrpc": "2.0",
  "error": {
    "code": 13,
    "message": "One of the provided IDs is not valid",
    "data": {
      "method": "VehicleInfo.GetDTCs"
    }
  }
}
```
