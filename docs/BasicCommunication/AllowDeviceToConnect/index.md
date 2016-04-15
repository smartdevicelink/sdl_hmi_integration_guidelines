## AllowDeviceToConnect
  * Type: Function
  * Sender: SDL
  * Purpose: Permit device to connect to head unit

### Behavior

!!! must

Check whether the device is allowed to connect to the head unit and response appropriately

!!!

!!! may

  1. Request the user's permission via VR, UI pop-up, etc.
  2. Implement a use case in which a user's device is not allowed to connect

!!!

### Request

#### Parameters

|Name|Type|Mandatory|Additional|Description|
|:---|:---|:--------|:---------|:----------|
|device|Common.DeviceInfo|true||Information about the device which is to be connected.|

#### DeviceInfo

|Name|Type|Mandatory|Additional|Description|
|:---|:---|:--------|:---------|:----------|
|name|String|true||The name of the device connected|
|id|String|true||The ID of the device connected. Either a hash of the device's USB serial number (in case of USB connection) or hash of device's MAC address (in case of BlueTooth or WiFi connection). Remains unique between the ignition cycles for the same transport type.|
|transportType|Common.TransportType|false||The transport type which the device is connected over to the HU (BlueTooth, USB or WiFi).<br>Always returned by SDL in OnAppRegistered and UpdateAppList RPCs.|
|isSDLAllowed|Boolean|false||Sent by SDL in `UpdateDeviceList`. ’true’ – if device is allowed for PolicyTable Exchange; ‘false’ – if device is NOT allowed for PolicyTable Exchange|

### Response

#### Parameters

|Name|Type|Mandatory|Additional|Description|
|:---|:---|:--------|:---------|:----------|
|allow|Boolean|true|||

### Example Request
```json
{
	"id" : 87,
	"jsonrpc" : "2.0",
	"method" : "BasicCommunication.AllowDeviceToConnect",
	"params" :
	[
		"deviceInfo" : {
				"name" : "Mary`s Phone",
				"id" : 8
		}
	]
}
```

### Example Response

```json
{
	"id" : 87,
	"jsonrpc" : "2.0",
	"result" :
	{
	 "allow" : true,
		"code" : 0,
		"method" : "BasicCommunication.AllowDeviceToConnect"
	}
}
```

### Error Message
```json
{
	"id" : 87,
	"jsonrpc" : "2.0",
	"error" :
	{
		"code" : 22,
		"message" : "An unknown error occurred",
		"data" :
		{
			"method" : "BasicCommunication.AllowDeviceToConnect"
		}
	}
}
```

### Sequence Diagrams
#### AllowDeviceToConnect Messaging
![Allow Device To Connect](./assets/AllowDeviceToConnect.png)
