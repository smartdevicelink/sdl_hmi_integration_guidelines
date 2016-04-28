## AddCommand


### Request

#### Parameters

|Name|Type|Mandatory|Additional|Description|
|:---|:---|:--------|:---------|:----------|
|cmdID|Integer|true|minvalue: 0<br>maxvalue: 2000000000||
|menuParams|Common.MenuParams|false|||
|cmdIcon|Common.Image|false|||
|appID|Integer|true|||

#### MenuParams

|Name|Type|Mandatory|Additional|Description|
|:---|:---|:--------|:---------|:----------|
|parentID|Integer|false|minvalue: 0<br>maxvalue: 2000000000||
|position|Integer|false|minvalue: 0<br>maxvalue: 1000||
|menuName|String|true|maxlength: 500||

#### Image

|Name|Type|Mandatory|Additional|Description|
|:---|:---|:--------|:---------|:----------|
|value|String|true|maxlength: 65535||
|imageType|Common.ImageType|true|||

### Response

#### Parameters

This RPC has no additional parameter requirements

### Sequence Diagrams
#### AddCommand Command Chosen By User
![AddCommand](./assets/AddCommandChosen.png)
#### AddCommand App Inactive
![AddCommand](./assets/AddCommandAppInactive.png)
#### AddCommand with sub menu
![AddCommand](./assets/AddCommandSubMenu.png)
#### AddCommand positions
![AddCommand](./assets/AddCommandPositions.png)
#### AddCommand Rejected Limit Reached
![AddCommand](./assets/AddCommandRejectedLimit.png)
#### AddCommand UI Succeeds, VR Fails
![AddCommand](./assets/AddCommandVRFail.png)
#### AddCommand UI Succeeds, VR Unresponsive
![AddCommand](./assets/AddCommandVRNoResponse.png)
#### AddCommand UI Fails, VR Succeeds
![AddCommand](./assets/AddCommandFailVRSuccess.png)
