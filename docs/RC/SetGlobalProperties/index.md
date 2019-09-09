## SetGlobalProperties

Type
: Function

Sender
: SDL

Purpose
: Inform HMI of user location properties set by the application in order to control RC modules

### Description
SDL requests to set the values of user location. The default `userLocation` should be `DRIVER`.  
Even if the driver's seat is out of the service area of a module, driver's app is still able to control any free module that is allowed by policy.

### Request
#### Behavior

!!! MUST   

1. Store the userLocation and associate it with appID.
2. Respond to the request.

!!!

#### Parameters
|Name|Type|Mandatory|Additional|
|:---|:---|:--------|:---------|
|userLocation|[Common.SeatLocation](../../common/structs/#seatlocation)|false||
|appID|Integer|true||


### Response

#### Parameters
This RPC has no additional parameter requirements


### Sequence Diagrams

|||
SetGlobalProperties
![SetGlobalProperties](assets/RC_SetGlobalProperties.png)
|||

### Example Request

```json
{
  "id":27,
  "jsonrpc":"2.0",
  "method":"RC.SetGlobalProperties",
  "params":{
     "appID":600980185,
     "userLocation":{
        "grid":{
           "col":2,
           "colspan":1,
           "level":0,
           "levelspan":1,
           "row":0,
           "rowspan":1
        }
     }
  }
}
```

### Example Response

```json
{
  "id" : 22,
  "jsonrpc" : "2.0",
  "result" :
  {
    "code" : 0,
    "method" : "RC.SetGlobalProperties"
  }
}
```

### Example Error

```json
{
  "id" : 22,
  "jsonrpc" : "2.0",
  "error" :
  {
    "code" : 22,
    "message" : "During API call the unknown error has occurred",
    "data" :
    {
      "method" : "RC.SetGlobalProperties"
    }
  }
}
```
