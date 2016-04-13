## GetListOfPermissions

### Request
#### Parameters
|Name|Type|Mandatory|Additional|Description|
|:---|:---|:--------|:---------|:----------|
|appID|Integer|false|||
### Response
#### Parameters
|Name|Type|Mandatory|Additional|Description|
|:---|:---|:--------|:---------|:----------|
|allowedFunctions|Common.PermissionItem|true|array: true<br>minsize: 0<br>maxsize: 100||
#### PermissionItem
|Name|Type|Mandatory|Additional|Description|
|:---|:---|:--------|:---------|:----------|
|name|String|true|||
|id|Integer|true|||
|allowed|Boolean|false|||
