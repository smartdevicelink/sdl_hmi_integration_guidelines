## GetURLS

### Request
#### Parameters
|Name|Type|Mandatory|Additional|Description|
|:---|:---|:--------|:---------|:----------|
|service|Integer|true|minvalue: 0<br>maxvalue: 100||
### Response
#### Parameters
|Name|Type|Mandatory|Additional|Description|
|:---|:---|:--------|:---------|:----------|
|urls|Common.ServiceInfo|false|array: true<br>minsize: 1<br>maxsize: 100||
#### ServiceInfo
|Name|Type|Mandatory|Additional|Description|
|:---|:---|:--------|:---------|:----------|
|url|String|true|||
|policyAppId|String|false|||
