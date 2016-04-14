## ActivateApp


### Request

#### Parameters

|Name|Type|Mandatory|Additional|Description|
|:---|:---|:--------|:---------|:----------|
|appID|Integer|true|||

### Response

#### Parameters

|Name|Type|Mandatory|Additional|Description|
|:---|:---|:--------|:---------|:----------|
|isSDLAllowed|Boolean|true|||
|device|Common.DeviceInfo|false|||
|isPermissionsConsentNeeded|Boolean|true|||
|isAppPermissionsRevoked|Boolean|true|||
|appRevokedPermissions|Common.PermissionItem|false|array: true<br>minsize: 1<br>maxsize: 100||
|isAppRevoked|Boolean|true|||
|priority|Common.AppPriority|false|||

#### DeviceInfo

|Name|Type|Mandatory|Additional|Description|
|:---|:---|:--------|:---------|:----------|
|name|String|true|||
|id|String|true|||
|transportType|Common.TransportType|false|||
|isSDLAllowed|Boolean|false|||

#### PermissionItem

|Name|Type|Mandatory|Additional|Description|
|:---|:---|:--------|:---------|:----------|
|name|String|true|||
|id|Integer|true|||
|allowed|Boolean|false|||

#### AppPriority

|Name|Value|
|:---|:----|
|EMERGENCY|0|
|NAVIGATION|1|
|VOICE_COMMUNICATION|2|
|COMMUNICATION|3|
|NORMAL|4|
|NONE|5|
