## StopStream

Type
: Notification

Sender
: SDL

Purpose
: Close the video streaming service between SDL and the HMI and stop streaming video data.

When an application closes the 11th service, SDL sends StopStream to HMI. It initiates the channel closure between SDL and HMI which is used for streaming video raw data sent by navigation or projection application. 


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

### Example Request

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
### Example Response

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

### Example Error

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
