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
