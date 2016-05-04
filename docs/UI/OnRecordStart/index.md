## OnRecordStart


### Notification

#### Parameters

|Name|Type|Mandatory|Additional|Description|
|:---|:---|:--------|:---------|:----------|
|appID|Integer|true|||

### Sequence Diagrams
|||
OnRecordStart with TTS.Speak
![OnRecordStart](./assets/OnRecordStartSpeak.png)
|||
|||
OnRecordStart without TTS.Speak
![OnRecordStart](./assets/OnRecordStartNoSpeak.png)
|||
|||
OnRecordStart not sent if UI.PerformAudioPassThru rejected
![OnRecordStart](./assets/OnRecordStartRejected.png)
|||

#### JSON Example Notification
```json

```
