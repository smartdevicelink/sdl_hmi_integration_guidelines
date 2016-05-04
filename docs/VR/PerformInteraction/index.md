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

### Sequence Diagrams
|||
PerformInteraction in VR Mode completed successfully
![PerformInteraction](./assets/PerformInteractionSuccess.png)
|||
|||
PerformInteraction in Manual Only Mode completed successfully
![PerformInteraction](./assets/PerformInteractionManualSuccess.png)
|||
|||
PerformInteraction in Both Mode times out
![PerformInteraction](./assets/PerformInteractionBothTimeout.png)
|||
