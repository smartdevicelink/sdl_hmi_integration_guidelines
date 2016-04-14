## OnAppPermissionConsent


### Notification

#### Parameters

|Name|Type|Mandatory|Additional|Description|
|:---|:---|:--------|:---------|:----------|
|appID|Integer|false|||
|consentedFunctions|Common.PermissionItem|true|array: true<br>minsize: 1<br>maxsize: 100||
|source|Common.ConsentSource|true|||

#### PermissionItem

|Name|Type|Mandatory|Additional|Description|
|:---|:---|:--------|:---------|:----------|
|name|String|true|||
|id|Integer|true|||
|allowed|Boolean|false|||

#### ConsentSource

|Name|Value|
|:---|:----|
|GUI|0|
|VUI|1|
