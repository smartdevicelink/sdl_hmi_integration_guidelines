## GetCapabilities

Type
: Function

Sender
: SDL

Purpose
: Inform SDL of the TTS capabilities of the vehicle.

### Request

#### Parameters

This RPC has no additional parameter requirements.

### Response

#### Parameters

|Name|Type|Mandatory|Additional|
|:---|:---|:--------|:---------|
|speechCapabilities|[Common.SpeechCapabilities](../../common/enums/#speechcapabilities)|true|array: true<br>minsize: 1<br>maxsize: 100|
|prerecordedSpeechCapabilities|[Common.PrerecordedSpeech](../../common/enums/#prerecordedspeech)|true|array: true<br>minsize: 1<br>maxsize: 100|

##### SpeechCapabilities

!!! NOTE

  Description of possible SpeechCapabilities
  TTS is performed by the HMI through:
  
  1. TEXT - Plain text format. TTSChunks with this type provide plain text to be spoken in the `text` field
  2. SAPI_PHONEMES - Microsoft Speech API Format. TTSChunks with this type provide a group of phonemes with this format in the `text` field
  3. LHPLUS_PHONEMES - LH+ Phoneme format. TTSChunks with this type provide a group of phonemes with this format in the `text` field
  4. PRE_RECORDED - Prerecorded sounds. TTSChunks with this type provide a value from [Common.PrerecordedSpeech](../../common/enums/index.md#prerecordedspeech) in the `text` field
  5. SILENCE - Definite amount of time. TTSChunks with this type provide amount of time HMI must keep silence.
  6. FILE - Uploaded audio files. TTSChunks with this type provide a filename pointing to an audio file previously uploaded through a PutFile RPC in the `text` field
      * These audio files can be in one of the following file types/specifications, all must be supported in order for the HMI to support the `FILE` option:
          * AUDIO_WAVE
              * Sample Rate: 16000 Hz
              * Bit Depth: 16
              * Mono Channel (1 Channel)
          * AUDIO_MP3
              * Sample Rate: 44100 Hz
              * Bit Depth: 8 - 320
              * Mono Channel (1 Channel)
          * AUDIO_AAC
              * Sample Rate: 44100 Hz
              * Bit Depth: 8 - 320
              * Mono Channel (1 Channel)

!!!

### Sequence Diagrams
|||
GetCapabilities
![GetCapabilities](./assets/GetCapabilities.png)
|||

### JSON Example Request

```json
{
  "id" : 13,
  "jsonrpc" : "2.0",
  "method" : "TTS.GetCapabilities"
}
```

### JSON Example Response

```json
{
  "id" : 13,
  "jsonrpc" : "2.0",
  "result" :
  {
    "capabilities" : ["TEXT"],
    "prerecordedSpeechCapabilities" : ["HELP_JINGLE", "INITIAL_JINGLE", "LISTEN_JINGLE", "POSITIVE_JINGLE", "NEGATIVE_JINGLE"],
    "code" : 0,
    "method" : "TTS.GetCapabilities"
  }
}
```

### JSON Example Error

```json
{
  "id" : 28,
  "jsonrpc" : "2.0",
  "error" :
  {
    "code" : 11,
    "message" : "The data sent is invalid",
    "data" :
    {
      "method" : "TTS.GetCapabilities"
    }
  }
}
```
