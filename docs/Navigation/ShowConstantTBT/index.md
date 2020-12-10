## ShowConstantTBT

Type
: Function

Sender
: SDL

Purpose
: Update navigation information of the embedded navigation system.

### Request

#### Parameters

|Name|Type|Mandatory|Additional|Description|
|:---|:---|:--------|:---------|:----------|
|navigationTexts|[Common.TextFieldStruct](../../common/structs/#textfieldstruct)|true|array: true<br>minsize: 0<br>maxsize: 5|See TextFieldStruct. Uses:<br>navigationText1<br>navigationText2<br>ETA<br>totalDistance<br>timeToDestination.|
|turnIcon|[Common.Image](../../common/structs/#image)|false||
|nextTurnIcon|[Common.Image](../../common/structs/#image)|false||
|distanceToManeuver|Float|true|minvalue: 0<br>maxvalue: 1000000000|Distance (in meters) until next maneuver. May be used to calculate progress bar.|
|distanceToManeuverScale|Float|true|minvalue: 0<br>maxvalue: 1000000000|Distance (in meters) from previous maneuver to next maneuver. May be used to calculate progress bar.|
|maneuverComplete|Boolean|false||If and when a maneuver has completed while an AlertManeuver is active, SDL will send this value set to TRUE in order to clear the AlertManeuver overlay.<br>If omitted the value should be assumed as FALSE.|
|softButtons|[Common.SoftButton](../../common/structs/#softbutton)|false|array: true<br>minsize: 0<br>maxsize: 3|Three dynamic SoftButtons available<br>If omitted on supported displays, the currently displayed SoftButton values will not change.|
|appID|Integer|true||ID of application related to this RPC.|

### Response

#### Parameters

This RPC has no additional parameter requirements

### Sequence Diagrams

|||
ShowConstantTBT
![ShowConstantTBT](./assets/ShowConstantTBT.jpg)
|||

### JSON Message Examples

#### Example Request

```json
{
  "id" : 543,
  "jsonrpc" : "2.0",
  "method" : "Navigation.ShowConstantTBT",
  "params" :
  {
    "navigationTexts" :
    [
      {
        "fieldName" :  "navigationText1",
        "fieldText" : "Destination point: Berlin"
      },
      {
        "fieldName" :  "ETA",
        "fieldText" : "15:45"
      },
      {
        "fieldName" :  "totalDistance",
        "fieldText" : "658"
      }
    ],
    "turnIcon" :
    {
         "value" : "tmp/SDL/app/Navi/icon_3245.jpeg",
         "imageType" : "DYNAMIC"
    },
    "distanceToManeuver" : 168.5,
    "distanceToManeuverScale" : 265.75,
    "softButtons" :
    {
        "type" :  "TEXT",
        "text" : "Close",
        "softButtonID" : 76,
        "systemAction" :  "DEFAULT_ACTION"
    },
    "appID" : 26743
  }
}
```

#### Example Response

```json
{
  "id" : 543,
  "jsonrpc" : "2.0",
  "result" :
  {
    "code" : 0,
    "method" : "Navigation.ShowConstantTBT"
  }
}
```

#### Example Error

```json
{
  "id" : 543,
  "jsonrpc" : "2.0",
  "error" :
  {
    "code" : 5,
    "message" : " A command was aborted",
    "data" :
    {
      "method" : "Navigation.ShowConstantTBT"
    }
  }
}
```
