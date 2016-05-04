## GetDTCs


### Request

#### Parameters

|Name|Type|Mandatory|Additional|Description|
|:---|:---|:--------|:---------|:----------|
|ecuName|Integer|true|minvalue: 0<br>maxvalue: 65535||
|dtcMask|Integer|false|minvalue: 0<br>maxvalue: 255||
|appID|Integer|true|||

### Response

#### Parameters

|Name|Type|Mandatory|Additional|Description|
|:---|:---|:--------|:---------|:----------|
|ecuHeader|Integer|true|minvalue: 0<br>maxvalue: 65535||
|dtc|String|false|array: true<br>minsize: 1<br>maxsize: 15<br>maxlength: 10||

### Sequence Diagrams
|||
GetDTCs
![GetDTCs](./assets/GetDTCs.png)
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
