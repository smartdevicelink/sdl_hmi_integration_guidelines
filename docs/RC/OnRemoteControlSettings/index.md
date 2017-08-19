## OnRemoteControlSettings

Type
: Notification

Sender
: HMI

Purpose
: Notification about remote-control settings and/or access mode changed. Sent after User`s choice through HMI.

RC.OnRemoteControlSettings is expected to be sent by HMI on system start up and every time user is changig remote control settings.
In case HMI does not send the notification on system start up, the default settings must be applied such as: remote control is allowed and access mode is "AUTO_ALLOW"
When user chose through HMI to disable remote control functionality the notification with allowed:false parameter must be sent to SDL

### Notification

#### Parameters

|Name|Type|Mandatory|Additional|Description|
|:---|:---|:--------|:---------|:---------|
|allowed|Boolean|false||If "true" - RC is allowed; if "false" - RC is disallowed|
|accessMode|[Common.RCAccessMode](https://github.com/OlesiaV/sdl_hmi_integration_guidelines/blob/2fecda9e5f0f4344a000092043c0530556a6bb8d/docs/Common/Enums/index.md)|false||The remote control access mode specified by the driver via HMI|

### Sequence Diagrams

|||
OnRemoteControlSettings
![OnRemoteControlSettings](https://github.com/OlesiaV/sdl_hmi_integration_guidelines/blob/sdl_rc_part3/docs/RC/OnRemoteControlSettings/accessories/OnRemoteControlSettings.png)
|||
|||
OnRemoteControlSettings disabling RC
![OnRemoteControlSettings disabling RC](https://github.com/OlesiaV/sdl_hmi_integration_guidelines/blob/sdl_rc_part3/docs/RC/OnRemoteControlSettings/accessories/OnRemoteControlSettings_disablingRC.png)
|||

#### JSON Example Notification

```json
{
    "jsonrpc": "2.0",
    "method": "RC.OnRemoteControlSettings",
    "params": {
        "accessMode": "ASK_DRIVER",
        "allowed": true
    }
}
```
