## SetAppIcon

Type
: Function

Sender
: SDL

Purpose
: Display the application's specified icon in the HMI's application list.

### Request

#### Parameters

|Name|Type|Mandatory|Additional|
|:---|:---|:--------|:---------|
|syncFileName|[Common.Image](../../common/structs/index.md#image)|true||
|appID|Integer|true||

### Response

#### Parameters

This RPC has no additional parameter requirements

### Sequence Diagrams
|||
SetAppIcon
![SetAppIcon](./assets/SetAppIcon.png)
|||

### Example Request

```json
{
  "id" : 88,
  "jsonrpc" : "2.0",
  "method" : "UI.SetAppIcon",
  "params" :
  {
    "syncFileName" :
    {
         "value" : "tmp/SDL/app/Best_Media/12345.jpg",
         "imageType" : "DYNAMIC"
    },
    "appID" : 65146
  }
}
```
### Example Response

```json
{
  "id" : 88,
  "jsonrpc" : "2.0",
  "result" :
  {
    "code" : 0,
   "method" : "UI.SetAppIcon"
  }
}
```

### Example Error

```json
{
  "id" : 88,
  "jsonrpc" : "2.0",
  "error" :
  {
    "code" : 2,
    "message" : "Unsupported resource",
    "data" :
    {
      "method" : "UI.SetAppIcon"
    }
  }
}
```
