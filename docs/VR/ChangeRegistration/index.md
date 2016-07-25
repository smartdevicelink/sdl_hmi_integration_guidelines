## ChangeRegistration

Type
: Function

Sender
: SDL

Purpose
: Change the language for voice recognition.

### Request

#### Parameters

|Name|Type|Mandatory|Additional|
|:---|:---|:--------|:---------|
|vrSynonyms|String|false|array: true<br>minsize: 1<br>maxsize: 100<br>maxlength: 40|
|language|[Common.Language](../../common/enums/#language)|true||
|appID|Integer|true||

### Response

#### Parameters

This RPC has no additional parameter requirements

### Sequence Diagrams
|||
ChangeRegistration
![ChangeRegistration](./assets/ChangeRegistration.png)
|||

### Example Request

```json
{
  "id" : 206,
  "jsonrpc" : "2.0",
  "method" : "VR.ChangeRegistration",
  "params" :
  {
    "language" : "DE-DE",
    "appID" : 13264
  }
}
```
### Example Response

```json
{
  "id" : 206,
  "jsonrpc" : "2.0",
  "result" :
  {
    "code" : 0,
    "method" : "VR.ChangeRegistration"
  }
}
```

### Example Error

```json
{
  "id" : 206,
  "jsonrpc" : "2.0",
  "error" :
  {
    "code" : 22,
    "message" : "The unknown error occurred",
    "data" :
    {
      "method" : "VR.ChangeRegistration"
    }
  }
}
```
