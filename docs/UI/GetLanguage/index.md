## GetLanguage

Type
: Function

Sender
: SDL

Purpose
: Inform SDL of the current HMI display language

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
  "id" : 167,
  "jsonrpc" : "2.0",
  "method" : "UI.GetLanguage"
}
```
### Example Response

```json
{
  "id" : 167,
  "jsonrpc" : "2.0",
  "result" :
  {
    "language" : "ES-ES",
    "code" : 0,
    "method" : "UI.GetLanguage"
  }
}
```

### Example Error

```json
{
  "id" : 167,
  "jsonrpc" : "2.0",
  "error" :
  {
    "code" : 11,
    "message" : "Invalid data",
    "data" :
    {
      "method" : "UI.GetLanguage"
    }
  }
}
```
