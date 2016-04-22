## GetSystemInfo

  * Type: Function
  * Sender: SDL
  * Purpose: Get head unit system information

!!! must

The HMI must respond to GetSystemInfo and provide the current head unit software version, language, and country code.

!!!

!!! note

When SDL starts, it sends GetSystemInfo to update the policies database with the latest system data. SDL Stores the ccpu_version when responding to RegisterAppInterfaceRequests.

!!!

### Request

#### Parameters

### Response

#### Parameters

|Name|Type|Mandatory|Additional|Description|
|:---|:---|:--------|:---------|:----------|
|ccpu_version|String|true|maxlength: 500|Software version of the module|
|language|Common.Language|true||ISO 639-1 combined with ISO 3166 alpha-2 country code (i.e. en-us)|
|wersCountryCode|String|true|maxlength: 500|Country code|

#### Language

|Name|Value|
|:---|:----|
|EN-US|0|
|ES-MX|1|
|FR-CA|2|
|DE-DE|3|
|ES-ES|4|
|EN-GB|5|
|RU-RU|6|
|TR-TR|7|
|PL-PL|8|
|FR-FR|9|
|IT-IT|10|
|SV-SE|11|
|PT-PT|12|
|NL-NL|13|
|EN-AU|14|
|ZH-CN|15|
|ZH-TW|16|
|JA-JP|17|
|AR-SA|18|
|KO-KR|19|
|PT-BR|20|
|CS-CZ|21|
|DA-DK|22|
|NO-NO|23|

### Example Request

```json
{
	"id" : 47,
	"jsonrpc" : "2.0",
	"method" : "BasicCommunication.GetSystemInfo"
}
```

### Example Response

```json
{
	"id" : 47,
	"jsonrpc" : "2.0",
	"result" : {
		"code" : 0,
		"method" : "BasicCommunication.GetSystemInfo",
    "params" : {
		    "ccpu_version" : "12.1.3",
		    "language" : "EN-US",
		    "wersCountryCode" : "WAEGB"
	      }
    }
}
```

### Example Error

```json
{
	"id" : 47,
	"jsonrpc" : "2.0",
	"error" :
	{
		"code" : 9,
		"message" : " Error in fetching system information ",
		"data" :
		{
			"method" : "BasicCommunication.GetSystemInfo"
		}
	}
}
```

### Sequence Diagrams
#### GetSystemInfo
![GetSysteminfo](./assets/GetSystemInfo.png)
