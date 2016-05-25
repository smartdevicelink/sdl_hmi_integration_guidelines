## IsReady

Type
: Function

Sender
: SDL

Purpose
: Request ready state of TTS Module

### Request

#### Parameters

|Name|Type|Mandatory|Additional|
|:---|:---|:--------|:---------|

### Response

#### Parameters

|Name|Type|Mandatory|Additional|
|:---|:---|:--------|:---------|
|available|Boolean|true||

### Sequence Diagrams
|||
IsReady
![IsReady](./assets/IsReady.png)
|||

### Example Request

```json
{
  "id" : 45,
  "jsonrpc" : "2.0",
  "method" : "TTS.IsReady"
}
```
### Example Response

```json
{
  "id" : 45,
  "jsonrpc" : "2.0",
  "result" :
  {
    "available" : true,
    "code" : 0,
    "method" : "TTS.IsReady"
  }
}
```

### Example Error

```json
{
  "id" : 45,
  "jsonrpc" : "2.0",
  "error" :
  {
    "code" : 11,
    "message" : "Invalid data",
    "data" :
    {
      "method" : "TTS.IsReady"
    }
  }
}
```
