## DeleteCommand


### Request

#### Parameters

|Name|Type|Mandatory|Additional|Description|
|:---|:---|:--------|:---------|:----------|
|cmdID|Integer|true|minvalue: 0<br>maxvalue: 2000000000||
|type|Common.VRCommandType|true|||
|grammarID|Integer|true|minvalue: 0<br>maxvalue: 2000000000||
|appID|Integer|true|||

#### VRCommandType

|Name|Value|
|:---|:----|
|Choice|0|
|Command|1|

### Response

#### Parameters

This RPC has no additional parameter requirements

### Sequence Diagrams
|||
DeleteCommand
![DeleteCommand](./assets/DeleteCommand.png)
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
