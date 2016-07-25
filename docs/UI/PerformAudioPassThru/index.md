## PerformAudioPassThru

Type
: Function

Sender
: SDL

Purpose
: Start audio capturing and sending PCM data to SDL

### Request

#### Parameters

|Name|Type|Mandatory|Additional|
|:---|:---|:--------|:---------|
|appID|Integer|true||
|audioPassThruDisplayTexts|[Common.TextFieldStruct](../../common/structs/#textfieldstruct)|true|array: true<br>minsize: 0<br>maxsize: 2|
|maxDuration|Integer|true|minvalue: 1<br>maxvalue: 1000000|
|muteAudio|Boolean|true||

### Response

#### Parameters

This RPC has no additional parameter requirements

### Sequence Diagrams
|||
PerformAudioPassThru requested with TTS.Speak
![PerformAudioPassThru](./assets/PerformAudioPassThruSpeak.png)
|||
|||
PerformAudioPassThru with EndAudioPassThru
![PerformAudioPassThru](./assets/PerformAudioPassThruEndAudio.png)
|||
|||
PerformAudioPassThru not supported
![PerformAudioPassThru](./assets/PerformAudioPassThruNotSupported.png)
|||
|||
PerformAudioPassThru from vehicle microphone
![PerformAudioPassThru](./assets/PerformAudioPassThruMic.png)
|||

### Example Request

```json
{
  "id" : 79,
  "jsonrpc" : "2.0",
  "method" : "UI.PerformAudioPassThru",
  "params" :
  {
    "audioPassThruDisplayTexts" :
    {
         "fieldName" :  audioPassThruDisplayText1,
     "fieldText" : "The audio capturing is in progress"
    },
    "maxDuration" : 10000,
  }
}
```
### Example Response

```json
{
  "id" : 79,
  "jsonrpc" : "2.0",
  "result" :
  {
    "code" : 0,
    "method" : "UI.PerformAudioPassThru"
  }
}
```

### Example Error

```json
{
  "id" : 79,
  "jsonrpc" : "2.0",
  "error" :
  {
    "code" : 7,
    "message" : "The user interrupted the RPC and indicated to start over",
    "data" :
    {
      "method" : "UI.PerformAudioPassThru"
    }
  }
}
```
