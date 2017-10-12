## OnSystemRequest

Type
: Notification

Sender
: SDL

Purpose
: A request from SDL to download data via a connected application.

**HTTP flow**

* SDL sends the PTS snapshot as binary data via an `OnSystemRequest` mobile request from the system to the backend. Both the "url" that the PTS will be forwarded to and the "timeout" must be taken from the Local Policy Table.
    * If no "url" is provided in the Local Policy Table, it is supposed that the mobile application will send the Policy Table Update data back to SDL.

`RequestType` defines the type of the requested data from a mobile device or the cloud. The HMI may request this data, but it's SDL's responsibility to block a `SystemRequest` in case the request intends to transfer a data type not allowed by the policy table.

HMI is informed about `requestTypes` that are allowed by policies via [OnAppPermissionChanged](../../sdl/onapppermissionchanged) and [OnAppRegistered](../onappregistered).

!!! NOTE   
  1. If HMI sends `OnSystemRequest` with a request type disallowed by the policy table, SDL will ignore it.   
  2. If HMI sends 'url' parameter within BasicCommunication.OnSystemRequest, SDL resends the 'url' parameter to mobile app via OnSystemRequest.   
  3. If HMI(SyncP) doesn't send any URLs to SDL, it is supposed that mobile application will sent Policy Table Update data back to SDL.
!!!

_**SyncP NOTE**_   
 1. It's SyncP responsibility to encrypt and encode PTS file and provide it to SDL via OnSystemRequest HMI API ("filename") parameter.      
 2. It's SyncP responsibility to choose an application for sending PTU and start timer (for future retry strategy) after sending OnSystemRequest to SDL.

!!! MUST   
HMI must send `OnSystemRequest`, if specific data is requested from the mobile device/cloud, or binary data needs to be sent to the mobile device.
!!!

### Notification

#### Parameters

|Name|Type|Mandatory|Additional|
|:---|:---|:--------|:---------|
|requestType|[Common.RequestType]|true||
|url|String|false|minlength: 1<br>maxlength: 1000|
|fileType|[Common.FileType]|false||
|offset|Integer|false|minvalue: 0<br>maxvalue: 100000000000|
|length|Integer|false|minvalue: 0<br>maxvalue: 100000000000|
|timeout|Integer|false|minvalue: 0<br>maxvalue: 2000000000|
|fileName|String|true|minlength: 1<br>maxlength: 255|
|appID|String|false|minlength: 1<br>maxlength: 50|

[Common.RequestType]: ../../common/enums/#requesttype
[Common.FileType]: ../../common/enums/#filetype

### Sequence Diagrams
|||
System Requests File Download
![OnSystemRequest](./assets/OnSystemRequest.png)
|||

|||
BC.OnSystemRequest in "Proprietary" Policy Table Update Flow
![Proprietary PTU](./assets/OnSystemRequest_in_Proprietary_PTU_flow.png)
|||

|||
BC.OnSystemRequest in External Proprietary Policy Table Update Flow
![EXTERNAL proprietary](../policyupdate/assets/diagram_PolicyUpdate_external_proprietary.png)
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
