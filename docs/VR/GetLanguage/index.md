## GetLanguage

Type
: Function

Sender
: SDL

Purpose
: Get the current voice recognition language.

### Request

#### Parameters

|Name|Type|Mandatory|Additional|
|:---|:---|:--------|:---------|

### Response

#### Parameters

|Name|Type|Mandatory|Additional|
|:---|:---|:--------|:---------|
|language|[Common.Language](../../common/enums/#language)|true||

### Sequence Diagrams
|||
GetLanguage
![GetLanguage](./assets/GetLanguage.png)
|||

### Example Request

```json
{
  "id" : 110,
  "jsonrpc" : "2.0",
  "method" : "VR.GetLanguage",
}
```
### Example Response

```json
{
  "id" : 110,
  "jsonrpc" : "2.0",
  "result" :
  {
    "language" : "DE-DE",
    "code" : 0,
    "method" : "VR.GetLanguage"
  }
}
```

### Example Error

```json
{
  "id" : 110,
  "jsonrpc" : "2.0",
  "error" :
  {
    "code" : 22,
    "message" : "During the API call the unknown error has occured",
    "data" :
    {
      "method" : "VR.GetLanguage"
    }
  }
}
```
