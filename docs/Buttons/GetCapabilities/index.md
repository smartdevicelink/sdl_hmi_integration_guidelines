## GetCapabilities

Type
: Function

Sender
: SDL

Purpose
: Get the capabilities of buttons in the vehicle.

### Request

SDL requests HMI to provide capabilities of supported buttons and saves received capabilities internally.

#### Parameters

This RPC has no additional parameter requirements

### Response

!!! must  

Check hmi_capabilities, and respond to SDL providing the capabilities of supported buttons.  

!!!

#### Parameters

|Name|Type|Mandatory|Additional|
|:---|:---|:--------|:---------|
|capabilities|[Common.ButtonCapabilities](../../common/structs/#buttoncapabilities)|true|array: true<br>minsize: 1<br>maxsize: 100|
|presetBankCapabilities|[Common.PresetBankCapabilities](../../common/structs/#presetbankcapabilities)|false||

### Sequence Diagrams

|||
GetCapabilities  
![GetCapabilities](./assets/GetCapabilities.png)
|||

### JSON Message Examples

#### Example Request

```json
{
  "id" : 20,
  "jsonrpc" : "2.0",
  "method" : "Buttons.GetCapabilities"
}
```

#### Example Response

```json
{
  "id" : 20,
  "jsonrpc" : "2.0",
  "result" :
  {
    "capabilities" :
    [
      {
        "name" : "OK",
        "shortPressAvailable" : true,
        "longPressAvailable" : true,
        "upDownAvailable" : true
      },
      {
        "name" : "SEEKLEFT",
        "shortPressAvailable" : true,
        "longPressAvailable" : true,
        "upDownAvailable" : true
      },
      {
        "name" : "SEEKRIGHT",
        "shortPressAvailable" : true,
        "longPressAvailable" : true,
        "upDownAvailable" : true
      },
      {
        "name" : "TUNEUP",
        "shortPressAvailable" : true,
        "longPressAvailable" : true,
        "upDownAvailable" : true
      },
      {
        "name" : "TUNEDOWN",
        "shortPressAvailable" : true,
        "longPressAvailable" : true,
        "upDownAvailable" : true
      }
    ],
    "presetBankCapabilities" :
    {
      "onScreenPresetsAvailable" : true
    },
    "code" : 0,
    "method" : "Buttons.GetCapabilities"
  }
}
```

#### Example Error

```json
{
  "id" : 20,
  "jsonrpc" : "2.0",
  "error" :
  {
    "code" : 9,
    "message" : "The requested data is not available",
    "data" :
    {
      "method" : "Buttons.GetCapabilities"
    }
  }
}
```
