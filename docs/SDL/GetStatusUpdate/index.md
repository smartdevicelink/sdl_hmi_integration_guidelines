## GetStatusUpdate

Type
: Function

Sender
: HMI

Purpose
: Get information about the current status of the policy update process.

### Request

In case HMI needs to find out current status of PTU and sends _GetStatusUpdate_request_ to SDL, it must respond with the current update status code to HMI.
The request _GetStatusUpdate_ duplicates the functionality of the notification _OnStatusUpdate_. In case the policy update status is being changed.(e.g. an update is finished successfully or retry strategy failed), SDL must send notification _OnStatusUpdate_ to HMI with the corresponding UpdateStatus code, whereas _GetStatusUpdate_ allowes to request the status of policy table at any time, not on update only.

_**HMI must:**_
Send a request to SDL if it needs to get a current policy update status according to its workflows.

#### Parameters

This RPC has no additional parameter requirements.

### Response

#### Parameters

|Name|Type|Mandatory|
|:---|:---|:--------|
|status|[Common.UpdateResult]|true|

[Common.UpdateResult]: https://github.com/smartdevicelink/sdl_hmi_integration_guidelines/blob/develop/docs/Common/Enums/index.md#updateresult

### Sequence Diagrams
|||
GetStatusUpdate
![GetStatusUpdate](./assets/GetStatusUpdate.jpg)
|||

### Example Request

```json
{
  "id" : 176,
  "jsonrpc" : "2.0",
  "method" : "SDL.GetStatusUpdate",
}
```
### Example Response

```json
{
  "id" : 176,
  "jsonrpc" : "2.0",
  "result" :
  {
    "status" : "UPDATE_NEEDED"
    "code" : 0,
    "method" : "SDL.GetStatusUpdate"
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
    "message" : "Some error occured",
    "data" :
    {
      "method" : "SDL.GetStatusUpdate"
    }
  }
}
```
