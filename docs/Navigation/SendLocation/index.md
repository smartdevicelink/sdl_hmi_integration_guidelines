## SendLocation

Type
: Function

Sender
: SDL

Purpose
: Allow a connected application to send a destination to the embedded navigation system.

### Request

#### Parameters

|Name|Type|Mandatory|Additional|
|:---|:---|:--------|:---------|
|appID|Integer|true||
|longitudeDegrees|Float|true|minvalue: -180<br>maxvalue: 180|
|latitudeDegrees|Float|true|minvalue: -90<br>maxvalue: 90|
|locationName|String|false|maxlength: 500|
|locationDescription|String|false|maxlength: 500|
|addressLines|String|false|array: true<br>minsize: 0<br>maxsize: 4<br>maxlength: 500|
|phoneNumber|String|false|maxlength: 500|
|locationImage|[Common.Image](../../common/structs/#image)|false||

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
{
  "id" : 138,
  "jsonrpc" : "2.0",
  "method" : "Navigation.SendLocation",
  "params" :
  {
    "longitudeDegrees" : 139.34,
    "latitudeDegrees" : 35.36,
    "locationName" : "Ford Repair",
    "locationImage" :
    {
         "value" : "tmp/SDL/app/Navi/12345.jpg",
         "imageType" : DYNAMIC
    }
  }
}
```
### Example Response

```json
{
  "id" : 138,
  "jsonrpc" : "2.0",
  "result" :
  {
    "code" : 0,
    "method" : "Navigation.SendLocation"
  }
}
```

### Example Error

```json
{
  "id" : 138,
  "jsonrpc" : "2.0",
  "error" :
  {
    "code" : 22,
    "message" : " The unknown issue occurred ",
    "data" :
    {
      "method" : "Navigation.SendLocation"
    }
  }
}
```
