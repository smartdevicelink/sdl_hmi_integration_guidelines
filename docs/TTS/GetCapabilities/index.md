## GetCapabilities


### Request

#### Parameters

|Name|Type|Mandatory|Additional|Description|
|:---|:---|:--------|:---------|:----------|

### Response

#### Parameters

|Name|Type|Mandatory|Additional|Description|
|:---|:---|:--------|:---------|:----------|
|speechCapabilities|Common.SpeechCapabilities|true|array: true<br>minsize: 1<br>maxsize: 5||
|prerecordedSpeechCapabilities|Common.PrerecordedSpeech|true|array: true<br>minsize: 1<br>maxsize: 5||

#### SpeechCapabilities

|Name|Value|
|:---|:----|
|TEXT|0|
|SAPI_PHONEMES|1|
|LHPLUS_PHONEMES|2|
|PRE_RECORDED|3|
|SILENCE|4|

#### PrerecordedSpeech

|Name|Value|
|:---|:----|
|HELP_JINGLE|0|
|INITIAL_JINGLE|1|
|LISTEN_JINGLE|2|
|POSITIVE_JINGLE|3|
|NEGATIVE_JINGLE|4|

### Sequence Diagrams
|||
GetCapabilities
![GetCapabilities](./assets/GetCapabilities.png)
|||
