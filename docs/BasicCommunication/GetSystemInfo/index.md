## GetSystemInfo

Type
: Function

Sender
: SDL

Purpose
: Get head unit system information

!!! must

The HMI must respond to GetSystemInfo and provide the current head unit software version, language, and country code.

!!!

!!! note

When SDL starts, it sends GetSystemInfo to update the policies database with the latest system data. SDL Stores the ccpu_version when responding to RegisterAppInterfaceRequests.

!!!

### Request

#### Parameters

This RPC has no additional parameter requirements

### Response

#### Parameters

|Name|Type|Mandatory|Additional|
|:---|:---|:--------|:---------|
|ccpu_version|String|true|maxlength: 500|
|language|[Common.Language](../../common/enums/#language)|true||
|wersCountryCode|String|true|maxlength: 500|

### Sequence Diagrams
|||
GetSystemInfo
![GetSysteminfo](./assets/GetSystemInfo.png)
|||

### JSON Message Examples

#### Example Request

```json
{
  "id" : 47,
  "jsonrpc" : "2.0",
  "method" : "BasicCommunication.GetSystemInfo"
}
```

#### Example Response

```json
{
  "id" : 47,
  "jsonrpc" : "2.0",
  "result" : {
    "code" : 0,
    "method" : "BasicCommunication.GetSystemInfo",
    "params" : {
        "ccpu_version" : "12.1.3",
        "language" : "EN-US",
        "wersCountryCode" : "WAEGB"
        }
    }
}
```

#### Example Error

```json
{
  "id" : 47,
  "jsonrpc" : "2.0",
  "error" :
  {
    "code" : 9,
    "message" : " Error in fetching system information ",
    "data" :
    {
      "method" : "BasicCommunication.GetSystemInfo"
    }
  }
}
```
