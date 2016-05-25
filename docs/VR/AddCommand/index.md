## AddCommand

Type
: Function

Sender
: SDL

Purpose
: Add a command for voice recognition

### Request

#### Parameters

|Name|Type|Mandatory|Additional|
|:---|:---|:--------|:---------|
|cmdID|Integer|true|minvalue: 0<br>maxvalue: 2000000000|
|vrCommands|String|true|array: true<br>minsize: 1<br>maxsize: 100<br>maxlength: 99|
|type|[Common.VRCommandType](../../common/enums/index.md#vrcommandtype)|true||
|grammarID|Integer|true|minvalue: 0<br>maxvalue: 2000000000|
|appID|Integer|false||

### Response

#### Parameters

This RPC has no additional parameter requirements

### Sequence Diagrams
|||
AddCommand
![AddCommand](./assets/AddCommand.png)
|||
|||
UI.AddCommand returns SUCCESS, VR.AddCommand fails
![AddCommand](./assets/AddCommandVRFail.png)
|||
|||
UI.AddCommand returns SUCCESS, VR.AddCommand no response
![AddCommand](./assets/AddCommandNoResponse.png)
|||
|||
UI.AddCommand fails, VR.AddCommand returns SUCCESS
![AddCommand](./assets/AddCommandSuccessUIFail.png)
|||
|||
UI.AddCommand no response, VR.AddCommand returns SUCCESS
![AddCommand](./assets/AddCommandSuccessUINoResponse.png)
|||

### Example Request

```json
{
  "id" : 119,
  "jsonrpc" : "2.0",
  "method" : "VR. AddCommand",
  "params" :
  {
    "cmdID" : 4365,
    "vrCommands" :
    [
         "Leave",
         "Exit",
         "Quit"
    ],
     "grammarID":123,
  "appID" : 64467
  }
}
```
### Example Response

```json
{
  "id" : 119,
  "jsonrpc" : "2.0",
  "result" :
  {
    "code" : 0,
    "method" : "VR.AddCommand"
  }
}
```

### Example Error

```json
{
  "id" : 119,
  "jsonrpc" : "2.0",
  "error" :
  {
    "code" : 13,
    "message" : "Provided appID is not valid",
    "data" :
    {
      "method" : "VR.AddCommand"
    }
  }
}
```
