## GetStatusUpdate

Type
: Function

Sender
: HMI

Purpose
: Get information about the current status of the policy update process.

### Request

#### Parameters

|Name|Type|Mandatory|Additional|
|:---|:---|:--------|:---------|

### Response

#### Parameters

|Name|Type|Mandatory|Additional|
|:---|:---|:--------|:---------|
|status|[Common.UpdateResult](../../common/enums/#updateresult)|true||

### Sequence Diagrams
|||
GetStatusUpdate
![GetStatusUpdate](./assets/GetStatusUpdate.jpg)
|||

### Example Request

```json
{
  "id" : 176,
  "jsonrpc" : "2.0",
  "method" : "SDL.GetStatusUpdate",
}
```
### Example Response

```json
{
  "id" : 176,
  "jsonrpc" : "2.0",
  "result" :
  {
    "status" : "UPDATE_NEEDED"
    "code" : 0,
    "method" : "SDL.GetStatusUpdate"
  }
}
```

### Example Error

```json
{
  "id" : 176,
  "jsonrpc" : "2.0",
  "error" :
  {
    "code" :22,
    "message" : "Some error occured",
    "data" :
    {
      "method" : "SDL.GetStatusUpdate"
    }
  }
}
```
