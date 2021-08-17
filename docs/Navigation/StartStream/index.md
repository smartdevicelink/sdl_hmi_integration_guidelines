## StartStream

Type
: Function

Sender
: SDL

Purpose
: Initiate a video streaming service between SDL and the HMI to stream video data.

### Request

#### Parameters

|Name|Type|Mandatory|Additional|
|:---|:---|:--------|:---------|
|url|String|true|minlength: 21|
|appID|Integer|true||

### Response

#### Parameters

This RPC has no additional parameter requirements

### Sequence Diagrams

|||
StartStream
![StartStream](./assets/StartStream.jpg)
|||

### JSON Message Examples

#### Example Request

```json
{
  "id" : 176,
  "jsonrpc" : "2.0",
  "method" : "Navigation.StartStream",
  "params" :  
  {
    "url" : "SDL/application_directory/video/123.mp4",
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
    "method" : "Navigation.StartStream"
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
    "message" : "Start stream failed or some other error occurred",
    "data" :
    {
      "method" : "Navigation.StartStream"
    }
  }
}
```
