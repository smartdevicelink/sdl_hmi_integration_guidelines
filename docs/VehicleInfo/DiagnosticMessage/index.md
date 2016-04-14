## DiagnosticMessage


### Request

#### Parameters

|Name|Type|Mandatory|Additional|Description|
|:---|:---|:--------|:---------|:----------|
|targetID|Integer|true|minvalue: 0<br>maxvalue: 65535||
|messageLength|Integer|true|minvalue: 0<br>maxvalue: 65535||
|messageData|Integer|true|array: true<br>minsize: 1<br>maxsize: 65535<br>minvalue: 0<br>maxvalue: 255||
|appID|Integer|true|||

### Response

#### Parameters

|Name|Type|Mandatory|Additional|Description|
|:---|:---|:--------|:---------|:----------|
|messageDataResult|Integer|true|array: true<br>minsize: 1<br>maxsize: 65535<br>minvalue: 0<br>maxvalue: 255||
