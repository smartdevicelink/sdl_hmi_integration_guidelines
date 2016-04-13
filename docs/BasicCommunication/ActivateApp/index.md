## ActivateApp

### Request
#### Parameters
|Name|Type|Mandatory|Additional|Description|
|:---|:---|:--------|:---------|:----------|
|appID|Integer|true|||
|priority|Common.AppPriority|false|||
|level|Common.HMILevel|false|||
#### AppPriority
|Name|Value|
|:---|:----|
|EMERGENCY|0|
|NAVIGATION|1|
|VOICE_COMMUNICATION|2|
|COMMUNICATION|3|
|NORMAL|4|
|NONE|5|
#### HMILevel
|Name|Value|
|:---|:----|
|FULL|0|
|LIMITED|1|
|BACKGROUND|2|
|NONE|3|
### Response
#### Parameters
This RPC has no additional parameter requirements
