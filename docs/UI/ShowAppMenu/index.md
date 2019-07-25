## ShowAppMenu

Type
: Function

Sender
: SDL

Purpose
: Show an app's menu or a corresponding sub-menu.

### Request

#### Parameters

|Name|Type|Mandatory|Additional|Description|
|:---|:---|:--------|:---------|:----------|
|menuID|Integer|false|minvalue: 1<br>maxvalue: 2000000000|If ommited the HMI opens the app's menu.<br>If set to a sub-menu ID the HMI opens the corresponding sub-menu previously added using `AddSubMenu`|
|appID|Integer|true|||

### Response

#### Parameters

This RPC has no additional parameter requirements

### Sequence Diagrams
|||
ShowAppMenu request(without menuID)
![ShowAppMenu](./assets/ShowAppMenu.png)
|||

|||
ShowAppMenu request(with menuID)
![ShowAppMenu](./assets/ShowAppMenu_MenuID.png)
|||
