## ChangeRegistration

Type
: Function

Sender
: SDL

Purpose
: Change the language of the TTS component.

### Request

#### Parameters

|Name|Type|Mandatory|Additional|Description|
|:---|:---|:--------|:---------|:--------------------------|
|appName|String|false||Request new app name registration<br>Needs to be unique over all applications from the same device.<br> May not interfere with any name or synonym of any registered applications form the same device.<br>Additional applications with the same name from the same device will be rejected|
|ngnMediaScreenAppName|String|false|maxlength: 100||
|language|[Common.Language](../../common/enums/#language)|true| | |
|appHMIType|[Common.AppHMIType](../../common/enums/##apphmitype)|false|minsize="1"<br>maxsize="100"<br>array="true"||
|appID|Integer|true||

### Response

#### Parameters

This RPC has no additional parameter requirements

### Sequence Diagrams
|||
ChangeRegistration after OnAppRegistered
![ChangeRegistration](./assets/ChangeRegistration.png)
|||

### Example Request

```json
{
  "id" : 206,
  "jsonrpc" : "2.0",
  "method" : "TTS.ChangeRegistration",
  "params" :
  {
    "language" : DE-DE,
    "appID" : 65539
  }
}
```
### Example Response

```json
{
  "id" : 206,
  "jsonrpc" : "2.0",
  "result" :
  {
    "code" : 0,
    "method" : "TTS.ChangeRegistration"
  }
}
```

### Example Error

```json
{
  "id" : 206,
  "jsonrpc" : "2.0",
  "error" :
  {
    "code" : 22,
    "message" : "Unknown error occurred",
    "data" :
    {
      "method" : "TTS.ChangeRegistration"
    }
  }
}
```
