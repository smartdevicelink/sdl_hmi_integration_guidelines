## AddCommand


### Request

#### Parameters

|Name|Type|Mandatory|Additional|Description|
|:---|:---|:--------|:---------|:----------|
|cmdID|Integer|true|minvalue: 0<br>maxvalue: 2000000000||
|vrCommands|String|true|array: true<br>minsize: 1<br>maxsize: 100<br>maxlength: 99||
|type|Common.VRCommandType|true|||
|grammarID|Integer|true|minvalue: 0<br>maxvalue: 2000000000||
|appID|Integer|false|||

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
AddCommand
![AddCommand](./assets/AddCommand.png)
|||
|||
UI.AddCommand returns SUCCESS, VR.AddCommand fails
![AddCommand](./assets/AddCommandVRFail.png)
|||
|||
UI.AddCommand returns SUCCESS, VR.AddCommand no response
![AddCommand](./assets/AddCommandNoResponse.png)
|||
|||
UI.AddCommand fails, VR.AddCommand returns SUCCESS
![AddCommand](./assets/AddCommandSuccessUIFail.png)
|||
|||
UI.AddCommand no response, VR.AddCommand returns SUCCESS
![AddCommand](./assets/AddCommandSuccessUINoResponse.png)
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
