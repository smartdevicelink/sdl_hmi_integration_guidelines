## AlertManeuver


### Request

#### Parameters

|Name|Type|Mandatory|Additional|Description|
|:---|:---|:--------|:---------|:----------|
|softButtons|Common.SoftButton|false|array: true<br>minsize: 0<br>maxsize: 3||
|appID|Integer|true|||

#### SoftButton

|Name|Type|Mandatory|Additional|Description|
|:---|:---|:--------|:---------|:----------|
|type|Common.SoftButtonType|true|||
|text|String|false|maxlength: 500||
|image|Common.Image|false|||
|isHighlighted|Boolean|false|||
|softButtonID|Integer|true|minvalue: 0<br>maxvalue: 65535||
|systemAction|Common.SystemAction|true|||

### Response

#### Parameters

This RPC has no additional parameter requirements

### Sequence Diagrams
|||
AlertManeuver Default Success Path
![AlertManeuver](./assets/AlertManeuverDefaultSuccess.jpg)
|||
|||
AlertManeuver from Background
![AlertManeuver](./assets/AlertManeuverBackground.jpg)
|||
|||
AlertManeuver Aborted
![AlertManeuver](./assets/AlertManeuverAborted.jpg)
|||
|||
AlertManeuver Rejected
![AlertManeuver](./assets/AlertManeuverRejected.jpg)
|||

### Example Request

```json
{
  "id": 143,
  "jsonrpc": "2.0",
  "method": "Navigation.AlertManeuver",
  "params": {
    "softButtons": [
      {
        "type": TEXT,
        "text": "Leave Onscreen",
        "softButtonID": 45,
        "systemAction": KEEP_CONTEXT
      },
      {
        "type": TEXT,
        "text": "Close",
        "softButtonID": 46,
        "systemAction": STEAL_FOCUS
      }
    ]
  },
  "appID": 96
}
```

### Example Response

```json
{
	"id" : 143,
	"jsonrpc" : "2.0",
	"result" :
	{
		"code" : 0,
		"method" : "Navigation.AlertManeuver"
	}
}
```

### Example Error

```json
{
	"id" : 143,
	"jsonrpc" : "2.0",
	"error" :
	{
		"code" : 13,
		"message" : "The command cannot be executed because there is NO app registered with the specified appID",
		"data" :
		{
			"method" : "Navigation.AlertManeuver"
		}
	}
}
```
