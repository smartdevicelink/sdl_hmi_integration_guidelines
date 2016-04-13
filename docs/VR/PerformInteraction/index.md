## PerformInteraction

### Request
#### Parameters
|Name|Type|Mandatory|Additional|Description|
|:---|:---|:--------|:---------|:----------|
|helpPrompt|Common.TTSChunk|false|array: true<br>minsize: 1<br>maxsize: 100||
|initialPrompt|Common.TTSChunk|false|array: true<br>minsize: 1<br>maxsize: 100||
|timeoutPrompt|Common.TTSChunk|false|array: true<br>minsize: 1<br>maxsize: 100||
|timeout|Integer|true|||
|grammarID|Integer|false|array: true<br>minsize: 1<br>maxsize: 100<br>minvalue: 0<br>maxvalue: 2000000000||
#### TTSChunk
|Name|Type|Mandatory|Additional|Description|
|:---|:---|:--------|:---------|:----------|
|text|String|true|maxlength: 500||
|type|Common.SpeechCapabilities|true|||
#### TTSChunk
|Name|Type|Mandatory|Additional|Description|
|:---|:---|:--------|:---------|:----------|
|text|String|true|maxlength: 500||
|type|Common.SpeechCapabilities|true|||
#### TTSChunk
|Name|Type|Mandatory|Additional|Description|
|:---|:---|:--------|:---------|:----------|
|text|String|true|maxlength: 500||
|type|Common.SpeechCapabilities|true|||
### Response
#### Parameters
|Name|Type|Mandatory|Additional|Description|
|:---|:---|:--------|:---------|:----------|
|choiceID|Integer|false|minvalue: 0<br>maxvalue: 2000000000||
