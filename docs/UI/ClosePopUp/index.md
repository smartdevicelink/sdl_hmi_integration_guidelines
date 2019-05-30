## ClosePopUp

Type
: Function

Sender
: SDL

Purpose
: Close the currently displayed popup UI element

### Request

#### Parameters

|Name|Type|Mandatory|Additional|
|:---|:---|:--------|:---------|
|methodName|String|false||

### Sequence Diagrams
|||
ClosePopUp for UI.PerformInteraction
![ClosePopUp](./assets/ClosePopUp.png)
|||

### Example Request

```json
{
  "id" : 79,
  "jsonrpc" : "2.0",
  "method" : "UI.ClosePopUp"
}
```
### Example Response

```json
{
  "id" : 79,
  "jsonrpc" : "2.0",
  "result" :
  {
    "code" : 0,
    "method" : "UI.ClosePopUp"
  }
}
```

### Example Error

```json
{
  "id" : 79,
  "jsonrpc" : "2.0",
  "error" :
  {
    "code" : 22,
    "message" : "During API call an unknown error has occurred",
    "data" :
    {
      "method" : "UI.ClosePopUp"
    }
  }
}
```
