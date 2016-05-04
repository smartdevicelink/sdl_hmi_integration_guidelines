## AddSubMenu


### Request

#### Parameters

|Name|Type|Mandatory|Additional|Description|
|:---|:---|:--------|:---------|:----------|
|menuID|Integer|true|minvalue: 1<br>maxvalue: 2000000000||
|menuParams|Common.MenuParams|true|||
|appID|Integer|true|||

#### MenuParams

|Name|Type|Mandatory|Additional|Description|
|:---|:---|:--------|:---------|:----------|
|parentID|Integer|false|minvalue: 0<br>maxvalue: 2000000000||
|position|Integer|false|minvalue: 0<br>maxvalue: 1000||
|menuName|String|true|maxlength: 500||

### Response

#### Parameters

This RPC has no additional parameter requirements

### Sequence Diagrams
|||
Add Sub Menu for Active App
![AddSubMenu](./assets/AddSubMenuActiveApp.png)
|||
|||
Add Sub Menu for Inactive App
![AddSubMenu](./assets/AddSubMenuInactiveApp.png)
|||
|||
Add Sub Menu with positions
![AddSubMenu](./assets/AddSubMenuPositions.png)
|||
|||
Add Sub Menu Rejected Limit Reached
![AddSubMenu](./assets/AddSubMenuLimit.png)
|||

### Example Request

```json

```
### Example Response

```json

```

### Example Error

```json

```
