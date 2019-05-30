## GetSupportedLanguages

Type
: Function

Sender
: SDL

Purpose
: Get the supported VR languages

### Request

#### Parameters

|Name|Type|Mandatory|Additional|
|:---|:---|:--------|:---------|

### Response

#### Parameters

|Name|Type|Mandatory|Additional|
|:---|:---|:--------|:---------|
|languages|[Common.Language](../../common/enums/#language)|true|array: true<br>minsize: 1<br>maxsize: 100|

### Example Request

```json
{
  "id" : 18,
  "jsonrpc" : "2.0",
  "method" : "VR.GetSupportedLanguages"
}
```
### Example Response

```json
{
  "id" : 18,
  "jsonrpc" : "2.0",
  "result" :
  {
    "languages" : ["AR-SA", "DE-DE", "EN-GB", "EN-US", "ES-ES", "FR-FR", "IT-IT"],
    "code" : 0,
    "method" : "VR.GetSupportedLanguages"
  }
}
```

### Example Error

```json
{
  "id" : 18,
  "jsonrpc" : "2.0",
  "error" :
  {
    "code" : 11,
    "message" : "The data sent is invalid",
    "data" :
    {
      "method" : "VR.GetSupportedLanguages"
    }
  }
}
```

### Sequence Diagrams
|||
GetSupportedLanguages
![GetSupportedLanguages](./assets/GetSupportedLanguages.png)
|||