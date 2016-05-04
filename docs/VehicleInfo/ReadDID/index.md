## ReadDID


### Request

#### Parameters

|Name|Type|Mandatory|Additional|Description|
|:---|:---|:--------|:---------|:----------|
|ecuName|Integer|true|minvalue: 0<br>maxvalue: 65535||
|didLocation|Integer|true|array: true<br>minsize: 1<br>maxsize: 1000<br>minvalue: 0<br>maxvalue: 65535||
|appID|Integer|true|||

### Response

#### Parameters

|Name|Type|Mandatory|Additional|Description|
|:---|:---|:--------|:---------|:----------|
|didResult|Common.DIDResult|false|array: true<br>minsize: 0<br>maxsize: 1000||

#### DIDResult

|Name|Type|Mandatory|Additional|Description|
|:---|:---|:--------|:---------|:----------|
|resultCode|Common.VehicleDataResultCode|true|||
|didLocation|Integer|true|minvalue: 0<br>maxvalue: 65535||
|data|String|false|maxlength: 5000||

### Sequence Diagrams
|||
ReadDID General Processing
![ReadDID](./assets/ReadDidGeneral.png)
|||
|||
ReadDID Expanded result
![ReadDID](./assets/ReadDidExpanded.png)
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
