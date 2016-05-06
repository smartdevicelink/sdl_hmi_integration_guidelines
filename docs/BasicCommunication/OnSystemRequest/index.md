## OnSystemRequest

Type
: Notification

Sender
: HMI

Purpose
: A request from the HMI to download data via a connected application.

### Notification

#### Parameters

|Name|Type|Mandatory|Additional|
|:---|:---|:--------|:---------|
|requestType|[Common.RequestType](../../Common/Enums/index.md#requesttype)|true||
|url|String|false|minlength: 1<br>maxlength: 1000|
|fileType|[Common.FileType](../../Common/Enums/index.md#filetype)|false||
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
