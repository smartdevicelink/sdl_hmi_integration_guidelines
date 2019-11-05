## UnpublishAppService

Type
: Function

Sender
: HMI

Purpose
: Delete a service previously published by the HMI on the module

### Request

#### Parameters

|Name|Type|Mandatory|Additional|
|:---|:---|:--------|:---------|
|serviceID|String|true||

### Response

#### Parameters

|Name|Type|Mandatory|Additional|
|:---|:---|:--------|:---------|
|||||

### JSON Message Examples

#### Example Request

```json
{
    "id": 1000,
    "jsonrpc": "2.0",
    "method": "AppService.UnpublishAppService",
    "params": {
        "serviceID": "1f89547cc0b12d5a52e896c45e141497f7af50e1e2dc8705914e75ef6fbeac03"
    }
}
```

#### Example Response

```json
{
    "id" : 1000,
    "jsonrpc" : "2.0",
    "result" : {
        "code" : 0,
        "method" : "AppService.UnpublishAppService"
    }
}
```

#### Example Error

```json
{
  "id" : 176,
  "jsonrpc" : "2.0",
  "error" :
  {
    "code" : 22,
    "message" : "Request timeout",
    "data" :
    {
      "method" : "AppService.UnpublishAppService"
    }
  }
}
```