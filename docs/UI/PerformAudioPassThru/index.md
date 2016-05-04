## PerformAudioPassThru


### Request

#### Parameters

|Name|Type|Mandatory|Additional|Description|
|:---|:---|:--------|:---------|:----------|
|appID|Integer|true|||
|audioPassThruDisplayTexts|Common.TextFieldStruct|true|array: true<br>minsize: 0<br>maxsize: 2||
|maxDuration|Integer|true|minvalue: 1<br>maxvalue: 1000000||
|muteAudio|Boolean|true|||

#### TextFieldStruct

|Name|Type|Mandatory|Additional|Description|
|:---|:---|:--------|:---------|:----------|
|fieldName|Common.TextFieldName|true|||
|fieldText|String|true|maxlength: 500||

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

```
### Example Response

```json

```

### Example Error

```json

```
