## OnServiceUpdate

Type
: Notification

Sender
: SDL

Purpose
: Update HMI with the status of a particular service

!!! must

The SDL must send OnServiceUpdate notification to provide accurate feedback to the user on the status of the system or what steps to take in case of an error.

!!!

### Notification
When a mobile navigation application is activated there is a series of steps taken. 
These steps include:
* getting the current system time,  
* performing a policy table update,  
* decrypting certificates and ensuring validity of the certificates.  
SDL should provide the status of these processes to HMI.

_Note:_ the only time when SDL would not be able provide the `appID` would be during the first StartService request for the RPC service before RAI was sent.

#### Parameters

|Name|Type|Mandatory|Additional|
|:---|:---|:--------|:---------|
|serviceType|[Common.ServiceType](../../common/structs/#moduledata)|true||
|serviceEvent|[Common.ServiceEvent]()|false||
|reason|[Common.ServiceUpdateReason]()|false||
|appID|Integer|false||

### Sequence Diagrams

|||
OnServiceUpdate
![OnServiceUpdate](assets/OnServiceUpdate.png)
|||

#### JSON Example Notification

```json
{
    "jsonrpc": "2.0",
    "method": "BC. OnServiceUpdate",
    "params": {
        "serviceType": "RPC",
        "serviceEvent":"REQUEST_RECEIVED"
              }
}
```