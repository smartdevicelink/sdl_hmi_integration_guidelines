## OnFindApplications

Type
: Notification

Sender
: HMI

Purpose
: Initiate the search for applications on the named device.

### Notification

On receipt of this notification, SDL will provide the list of registered applications for the named device via the 'UpdateAppList' RPC.

!!! NOTE

SDL ignores all invalid notifications sent from the HMI (e.g. invalid JSON, invalid data types).

!!!

!!! MUST

HMI must send an 'OnFindApplications' notification when the user requests to find applications on a device (i.e. user chooses a device from a list of devices).

!!!

#### Parameters

|Name|Type|Mandatory|Additional|
|:---|:---|:--------|:---------|
|deviceInfo|[Common.DeviceInfo](../../common/structs/#deviceinfo)|false||

### Sequence Diagrams

|||
User Choice After OnAppRegistered
![OnFindApplications](./assets/OnFindApplications.png)
|||
|||
OnFindApplications after Device Chosen by User
![OnFindApplications](./assets/OnFindApplicationsDeviceChosen.png)
|||

### JSON Message Examples

#### Example Notification

```json
{
  "jsonrpc" : "2.0",
  "method" : "BasicCommunication.OnFindApplications",
  "params" :
  {
    "deviceinfo" :
      {
        "name" : "XT910",
        "id" : 4
      }
  }
}
```
