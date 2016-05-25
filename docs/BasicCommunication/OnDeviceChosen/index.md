## OnDeviceChosen

Type
: Notification

Sender
: HMI

Purpose
: Open the connection with the named device

On Receipt of this notification SDL will open the connected with the named device and start sessions with the compatible SDL applications running on the device.

!!! must

  1. Provide the user with the possibility to choose among the list of known devices
  2. Send this RPC when the user has selected the device

!!!

!!! note

The list of known devices is provided to the HMI in the [UpdateDeviceList](../UpdateDeviceList) Request.

!!!

### Notification

#### Parameters

|Name|Type|Mandatory|Additional|
|:---|:---|:--------|:---------|
|deviceInfo|[Common.DeviceInfo](../../Common/Structs/index.md#deviceinfo)|true||

### Example Notification
```json
{
  "jsonrpc" : "2.0",
  "method" : "BasicCommunication.OnDevcieChosen",
  "params" :
  {
    "deviceInfo" :
    {
        "name" : "Jerry`s Phone",
        "id" : 3
    }
  }
}
```

### Sequence Diagrams
|||
OnDeviceChosen
![OnDeviceChosen](./assets/OnDeviceChosen.png)
|||
