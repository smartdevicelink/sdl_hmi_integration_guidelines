## OnSystemRequest

Type
: Notification

Sender
: HMI

Purpose
: A request from the HMI to download data via a connected application.

An `OnSystemRequest` is a notification that can be used for a couple of different purposes:

  * As an asynchronous request from the HMI/Core for specific data from the mobile device or cloud.
  * As a response to a request from the device or cloud. In this case binary data could be included in the hybrid part of the message to the mobile device.
  * As a request to the mobile side to stop a current upload/data transfer via a `PutFile`.

`RequestType` defines the type of the requested data from a mobile device or the cloud. The HMI may request this data, but it's SDL's responsibility to block a `SystemRequest` in case the request intends to transfer a data type not allowed by the policy table.

The HMI is informed about `requestTypes` that are allowed by policies via [OnAppPermissionChanged](../../sdl/onapppermissionchanged) and [OnAppRegistered](../onappregistered).

!!! NOTE

If the HMI sends `OnSystemRequest` with a request type disallowed by the policy table, SDL will ignore it.

!!!

!!! MUST

HMI must send `OnSystemRequest` if specific data is requested from the mobile device/cloud, or binary data needs to be sent to the mobile device.

!!!
### Notification

#### Parameters

|Name|Type|Mandatory|Additional|
|:---|:---|:--------|:---------|
|requestType|[Common.RequestType](../../common/enums/#requesttype)|true||
|url|String|false|minlength: 1<br>maxlength: 1000|
|fileType|[Common.FileType](../../common/enums/#filetype)|false||
|offset|Integer|false|minvalue: 0<br>maxvalue: 100000000000|
|length|Integer|false|minvalue: 0<br>maxvalue: 100000000000|
|timeout|Integer|false|minvalue: 0<br>maxvalue: 2000000000|
|fileName|String|true|minlength: 1<br>maxlength: 255|
|appID|String|false|minlength: 1<br>maxlength: 50|

### Sequence Diagrams
|||
System Requests File Download
![OnSystemRequest](./assets/OnSystemRequest.png)
|||

#### JSON Example Notification
```json
{
  "jsonrpc" : "2.0",
  "method" : "BasicCommunication.OnSystemRequest",
  "params" :
  {
    "fileName":"/fs/images/ivsu_cache/EncodedPolicyTable.json",
     "fileType":"JSON",
     "length":0,
     "offset":0,
     "requestType":"PROPRIETARY",
     "timeout":1000,
     "url":"https://policies.smartdevicelink.org/api/1/policies"
    }
}
```
