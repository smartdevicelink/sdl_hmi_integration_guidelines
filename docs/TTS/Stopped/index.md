## Stopped


### Notification

### Sequence Diagrams
|||
Stopped after StopSpeaking from SDL
![Stopped](./assets/Stopped.png)
|||

### Example Request

```json
{
	"jsonrpc" : "2.0",
	"method" : " TTS.Stopped",
}
```
### Example Response

```json
{
	"id" : 37,
	"jsonrpc" : "2.0",
	"result" :
	{
		"code" : 0,
		"method" : "TTS.Stopped"
	}
}
```

### Example Error

```json
{
	"id" : 37,
	"jsonrpc" : "2.0",
	"error" :
	{
		"code" : 22,
		"message" : "Something went wrong",
		"data" :
		{
			"method" : "TTS.Stopped"
		}
	}
}
```
