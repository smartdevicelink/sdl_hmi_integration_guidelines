## GetUserFriendlyMessage


### Request

#### Parameters

|Name|Type|Mandatory|Additional|
|:---|:---|:--------|:---------|
|messageCodes|String|true|array: true<br>minsize: 1<br>maxsize: 100<br>maxlength: 500|
|language|[Common.Language](../../Common/Enums/index.md#language)|false||

### Response

#### Parameters

|Name|Type|Mandatory|Additional|
|:---|:---|:--------|:---------|
|messages|[Common.UserFriendlyMessage](../../Common/Structs/index.md#userfriendlymessage)|false|array: true<br>minsize: 1<br>maxsize: 100|

### Sequence Diagrams
|||
GetUserFriendlyMessage for device consent
![GetUserFriendlyMessage](./assets/GetUserFriendlyMessage.png)
|||

### Example Request

```json
{
  "id" : 176,
  "jsonrpc" : "2.0",
  "method" : "SDL.GetUserFriendlyMessage",
  "params" :
  {
    "messageCodes": "AppPermissions",    
      "language" : "EN-GB"
  }

}
```
### Example Response

```json
{
  "id" : 176,
  "jsonrpc" : "2.0",
  "result" :
  {
    "messages": {
             "messageCode": "AppPermissions",
             "ttsString": "%appName% is requesting the use of the following ....",
             line1: "Grant Requested",
             line2: "Permission(s)?"
            },
    "code" : 0,
    "method" : "SDL.GetUserFriendlyMessage"
  }
}
```

### Example Error

```json
{
  "id" : 176,
  "jsonrpc" : "2.0",
  "error" :
  {
    "code" :22,
    "message" : "Some error occurred",
    "data" :
    {
      "SDL.GetUserFriendlyMessage"
    }
  }
}
```
