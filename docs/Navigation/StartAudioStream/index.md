## StartAudioStream

Type
: Function

Sender
: SDL

Purpose
: Initiate an audio streaming service between SDL and the HMI to stream audio data.

### Request

#### Parameters

|Name|Type|Mandatory|Additional|
|:---|:---|:--------|:---------|
|url|String|true|minlength: 21<br>maxlength: 500|
|appID|Integer|true||

### Response

#### Parameters

This RPC has no additional parameter requirements

### Sequence Diagrams
|||
StartAudioStream
![StartAudioStream](./assets/StartAudioStream.jpg)
|||

### Example Request

```json
{
  "jsonrpc" : "2.0",
  "method" : "Navigation.StartAudioStream",
  "params" :  
  {
    "url" : "SDL/application_directory/audio/123.mp3",
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
    "method" : "Navigation.StartAudioStream"
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
    "message" : "Start stream failed or some other error occurred",
    "data" :
    {
      "method" : "Navigation.StartAudioStream"
    }
  }
}
```
