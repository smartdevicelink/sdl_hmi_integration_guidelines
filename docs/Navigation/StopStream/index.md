## StopStream

Type
: Function

Sender
: SDL

Purpose
: Close the video streaming service between SDL and the HMI and stop streaming video data.

The app must stop video streaming after receiving onHMIStatus with videoStreamingState=NOT_STREAMBLE. 
If the app does not stop streaming after certain amount of time, SDL sends a StopService Control Frame to the app in protocol layer.

### Request

#### Parameters

|Name|Type|Mandatory|Additional|
|:---|:---|:--------|:---------|
|appID|Integer|true||

### Response

#### Parameters

This RPC has no additional parameter requirements

### Sequence Diagrams
|||
StopStream
![StopStream](./assets/StopStream.jpg)
|||

### JSON Message Examples

#### Example Request

```json
{
  "jsonrpc" : "2.0",
  "method" : "Navigation.StopStream",
  "params" :  
  {
    "appID" : 65674
  }
}
```

#### Example Response

```json
{
  "id" : 176,
  "jsonrpc" : "2.0",
  "result" :
  {
    "code" : 0,
    "method" : "Navigation.StopStream"
  }
}
```

#### Example Error

```json
{
  "id" : 176,
  "jsonrpc" : "2.0",
  "error" :
  {
    "code" : 22,
    "message" : "Stop stream failed or some other error occurred",
    "data" :
    {
      "method" : "Navigation.StopStream"
    }
  }
}
```
