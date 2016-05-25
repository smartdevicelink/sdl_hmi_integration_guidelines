## GetCapabilities

Type
: Function

Sender
: SDL

Purpose
: Inform SDL of the VR capabilities of the vehicle.

### Request

#### Parameters

|Name|Type|Mandatory|Additional|
|:---|:---|:--------|:---------|

### Response

#### Parameters

|Name|Type|Mandatory|Additional|
|:---|:---|:--------|:---------|
|vrCapabilities|[Common.VrCapabilities](../../common/enums/index.md#vrcapabilities)|false|array: true<br>minsize: 1<br>maxsize: 100|

### Sequence Diagrams
|||
GetCapabilities
![GetCapabilities](./assets/GetCapabilities.png)
|||

### Example Request

```json
{
  "id" : 9,
  "jsonrpc" : "2.0",
  "method" : "VR.GetCapabilities"
}
```
### Example Response

```json
{
  "id" : 9,
  "jsonrpc" : "2.0",
  "result" :
  {
    "vrCapabilities" : [TEXT],
    "code" : 0,
    "method" : "VR.GetCapabilities"
  }
}
```

### Example Error

```json
{
  "id" : 9,
  "jsonrpc" : "2.0",
  "error" :
  {
    "code" : 11,
    "message" : "The data sent is invalid",
    "data" :
    {
      "method" : "VR.GetCapabilities"
    }
  }
}
```
