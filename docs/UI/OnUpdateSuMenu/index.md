## OnUpdateFile

Type
: Notification

Sender
: HMI

Purpose
: For the HMI to tell Core that a submenu needs updating

### Notification

### Parameters
|Name|Type|Mandatory|Additional|
|:---|:---|:--------|:---------|
|appID|Integer|true||
|menuID|Integer|true|minvalue: 0 <br> maxvalue: 2000000000|
|updateSubCells|Boolean|false||
### Sequence Diagrams

|||
Requesting submenu contents to be updated
![OnUpdateSubMenu](./assets/OnUpdateSubMenu.png)
|||


### JSON Message Examples

#### Example Notification

```json
{
  "jsonrpc" : "2.0",
  "method" : "UI.OnUpdateSubMenu",
  "params" :
  {
    "appID": 12345678,
    "menuID": 1,
    "updateSubCells": true
  }
}