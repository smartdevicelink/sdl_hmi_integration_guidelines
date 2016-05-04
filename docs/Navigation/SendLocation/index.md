## SendLocation


### Request

#### Parameters

|Name|Type|Mandatory|Additional|Description|
|:---|:---|:--------|:---------|:----------|
|appID|Integer|true|||
|longitudeDegrees|Float|true|minvalue: -180<br>maxvalue: 180||
|latitudeDegrees|Float|true|minvalue: -90<br>maxvalue: 90||
|locationName|String|false|maxlength: 500||
|locationDescription|String|false|maxlength: 500||
|addressLines|String|false|array: true<br>minsize: 0<br>maxsize: 4<br>maxlength: 500||
|phoneNumber|String|false|maxlength: 500||
|locationImage|Common.Image|false|||

#### Image

|Name|Type|Mandatory|Additional|Description|
|:---|:---|:--------|:---------|:----------|
|value|String|true|maxlength: 65535||
|imageType|Common.ImageType|true|||

### Response

#### Parameters

This RPC has no additional parameter requirements

### Sequence Diagram
|||
SendLocation Success
![SendLocation](./assets/SendLocationSuccess.jpg)
|||
|||
SendLocation Fail with warnings
![SendLocation](./assets/SendLocationFailWarning.jpg)
|||
|||
SendLocation Fail Rejected
![SendLocation](./assets/SendLocationFailRejected.jpg)
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
