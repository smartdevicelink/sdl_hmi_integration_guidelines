## GetListOfPermissions

Type
: Function

Sender
: HMI

Purpose
: Get the list of permissions for the specified application or for all applications.

### Request

#### Parameters

|Name|Type|Mandatory|Additional|
|:---|:---|:--------|:---------|
|appID|Integer|false||

### Response

#### Parameters

|Name|Type|Mandatory|Additional|
|:---|:---|:--------|:---------|
|allowedFunctions|[Common.PermissionItem](../../common/structs/index.md#permissionitem)|true|array: true<br>minsize: 0<br>maxsize: 100|

### Sequence Diagrams
|||
GetListOfPermissions
![GetListOfPermissions](./assets/GetListOfPermissions.jpg)
|||
|||
GetListOfPermissions without AppId
![GetListOfPermissions](./assets/GetListOfPermissionsNoId.jpg)
|||

### Example Request

```json
{
  "id" : 143,
  "jsonrpc" : "2.0",
  "method" : "SDL.GetListOfPermissions",
  "params" :
  {
    "appID" : 65596
  }
}
```
### Example Response

```json
{
  "id" : 143,
  "jsonrpc" : "2.0",
  "result" :
  {
    "allowedFunctions" :

[
      {
    "name" : "Location-1",
      "id":1234,
      "allowed":true
  },

     {
    "name" : "Notifications",
      "id":76876,
      "allowed":false
  },

    ]

    "code" : 0,
    "method" : "SDL.GetListOfPermissions"
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
    "code" : 15,
    "message" : " A command cannot be executed because there is NO specified         with appID application registered ",
    "data" :
    {
      "method" : "SDL.GetListOfPermissions"
    }
  }
}
```
