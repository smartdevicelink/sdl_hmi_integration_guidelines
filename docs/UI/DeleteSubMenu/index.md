## DeleteSubMenu

Type
: Function

Sender
: SDL

Purpose
: Delete a sub menu from the specified application's menu

### Request

#### Parameters

|Name|Type|Mandatory|Additional|
|:---|:---|:--------|:---------|
|menuID|Integer|true|minvalue: 1<br>maxvalue: 2000000000|
|appID|Integer|true||

### Response

#### Parameters

This RPC has no additional parameter requirements

### Sequence Diagrams
|||
Delete Sub Menu Containing Commands
![DeleteSubMenu](./assets/DeleteSubMenuWithCommands.png)
|||
|||
Delete Sub Menu that is on screen
![DeleteSubMenu](./assets/DeleteSubMenuOnScreen.png)
|||

### Example Request

```json
{
  "id" : 70,
  "jsonrpc" : "2.0",
  "method" : "UI. DeleteSubMenu",
  "params" :
  {
    "menuID" : 345,
    "appID" : 65464
  }
}
```
### Example Response

```json
{
  "id" : 70,
  "jsonrpc" : "2.0",
  "result" :
  {
    "code" : 0,
    "method" : "UI. DeleteSubMenu"
  }
}
```

### Example Error

```json
{
  "id" : 70,
  "jsonrpc" : "2.0",
  "error" :
  {
    "code" : 8,
    "message" : "The data may not be changed because it is currently in use",
    "data" :
    {
      "UI. DeleteSubMenu "
    }
  }
}
```
