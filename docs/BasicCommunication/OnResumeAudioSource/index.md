## OnResumeAudioSource

Type
: Notification

Sender
: SDL

Purpose
: Inform the HMI that an application being resumed needs to become audible.


### Notification

#### Parameters

|Name|Type|Mandatory|Additional|Description|
|:---|:---|:--------|:---------|:----------|
|appID|Integer|true|||

### Sequence Diagrams
|||
Audio Source Resumption for App in FULL
![OnResumeAudioSource](./assets/OnResumeAudioSourceFull.png)
|||
|||
Audio Source Resumption for App in LIMITED
![OnResumeAudioSource](./assets/OnResumeAudioSourceLimited.png)
|||
|||
Audio Source Resumption after Phone Call
![OnResumeAudioSource](./assets/OnResumeAudioSourcePhone.png)
|||
|||
Audio Source Resume one audio app one phone call app
![OnResumeAudioSource](./assets/OnResumeAudioSourceMultiple.png)
|||

#### JSON Example Notification
```json
{
	"jsonrpc" : "2.0",
	"method" : "BasicCommunication.OnResumeAudioSource"
     "params" :
	 {
		  "appID" : 123
 	 }

}
```
