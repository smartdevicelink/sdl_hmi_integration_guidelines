## OnRCStatus

Type
: Notification

Sender
: SDL

Purpose
: Inform HMI and mobile application about changes in RC module allocation.

!!! must


### Notification

SDL must send OnRCStatus notification when
 * RC application registers with SDL
 * a module is allocated to an application 
 * a module is de-allocated from an application (the module is freed when application exits, disconnects, goes to HMI level NONE)
 * when an application no longer has the right to control the module (for example, a policy update can revoke the application's access to a module)

#### Parameters

|Name|Type|Mandatory|Additional|
|:---|:---|:--------|:---------|
|appID|Integer|true|ID of selected application|
|allocatedModules|[Common.ModuleData](/docs/Common/Structs/index.md)|true|Contains a list (zero or more) of module types that are allocated to the application|
|freeModules|[Common.ModuleData](/docs/Common/Structs/index.md)|true|Contains a list (zero or more) of module types that are free to access for the application|

### Sequence Diagrams

|||
OnRCStatus
![OnRCStatus](assets/OnRCStatus.png)
|||

#### JSON Example Notification

```json
{
    "jsonrpc": "2.0",
    "method": "RC.OnRCStatus",
    "params": {
        "allocatedModules" : [],
        "freeModules" : [
     {
        "moduleType" : "CLIMATE"
     },
     {
        "moduleType" : "RADIO"
     },
     {
        "moduleType" : "AUDIO"
     },
     {
        "moduleType" : "LIGHT"
     },
     {
        "moduleType" : "HMI_SETTINGS"
     },
     {
        "moduleType" : "SEAT"
     }
  ]
}