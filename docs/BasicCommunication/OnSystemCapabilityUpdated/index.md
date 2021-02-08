## OnSystemCapabilityUpdated

Type
: Notification

Sender
: SDL or HMI

Purpose
: Inform that a specific system capability has changed

### Notification

1. HMI sends OnSystemCapabilityUpdated notification to SDL after creating a widget _(see also [CreateWindow](../../UI/CreateWindow/index.md))_.
2. HMI sends OnSystemCapabilityUpdated notification after receiving UI.Show(templateConfiguration) request manipulating the content presented of main window or widgets.
3. HMI should not send `WEB_VIEW` template in `WindowCapability` for any widgets, and applications with `AppHMIType` other than `WEB_VIEW`.
4. If the application changes template to `WEB_VIEW`, HMI should send OnSystemCapabilityUpdated with the following `textFields` restrictions in `WindowCapability`:
    * `menuName` and `templateTitle` should be included, if they are visible on HMI.
    * `mainField1-4`, `statusBar` and `mediaTrack` should not be included if OEM implemented the `WEB_VIEW` template without these text fields.
    * `availabletemplates`, `buttonCapabilities` and `imageTypeSupported` should reflect the general capabilities of the window/system.
5. HMI may send `KeyboardCapabilities` within OnSystemCapabilityUpdated notification which may include `maskInputCharactersSupported`, `supportedKeyboards` and `configurableKeys` parameters.

!!! NOTE

1. Template `WEB_VIEW` is only allowed for the WebEngine applications with `AppHMIType`=`WEB_VIEW`.

2. In case HMI sends OnSystemCapabilityUpdated notification with `KeyboardCapabilities`, `supportedKeyboards` and without information about `numConfigurableKeys`, SDL would provide `KeyboardCapabilities` to app with `numConfigurableKeys` set to zero.
!!!

#### Parameters

|Name|Type|Mandatory|Additional|
|:---|:---|:--------|:---------|
|systemCapability|[Common.SystemCapability](../../common/structs/#systemcapability)|true||
|appID|Integer|false||

### Sequence Diagrams

|||
OnSystemCapabilityUpdated(APP_SERVICES, PUBLISHED)
![OnSystemCapabilityUpdated_PUBLISHED](./assets/OnSystemCapabilityUpdated_PUBLISHED.png)
|||

|||
OnSystemCapabilityUpdated(APP_SERVICES, REMOVED)
![OnSystemCapabilityUpdated_REMOVED](./assets/OnSystemCapabilityUpdated_REMOVED.png)
|||

### JSON Message Examples

#### Example Notification

```json
{
  "jsonrpc": "2.0",
  "method": "BasicCommunication.OnSystemCapabilityUpdated",
  "params": {
    "systemCapability": {
      "appServicesCapabilities": {
        "appServices": [
          {
            "updatedAppServiceRecord": {
              "serviceActive": true,
              "serviceID": "c9503a4f983e3dd31a7a14564d405cdf84769c9b9a71cae9cc211a0b74e93629",
              "serviceManifest": {
                "allowAppConsumers": true,
                "rpcSpecVersion": {
                  "majorVersion": 5,
                  "minorVersion": 1,
                  "patchVersion": 0
                },
                "serviceName": "Mobile Media Service",
                "serviceType": "MEDIA"
              },
              "servicePublished": true
            }
          },
          {
            "updateReason": "PUBLISHED",
            "updatedAppServiceRecord": {
              "serviceActive": false,
              "serviceID": "d6d8d2fb2bfcc00033804fb19e9fb7d6070d2c166f49881563276f17478c39f8",
              "serviceManifest": {
                "allowAppConsumers": true,
                "rpcSpecVersion": {
                  "majorVersion": 5,
                  "minorVersion": 1,
                  "patchVersion": 0
                },
                "serviceName": "Waze Music",
                "serviceType": "MEDIA"
              },
              "servicePublished": true
            }
          }
        ]
      },
      "systemCapabilityType": "APP_SERVICES"
    }
  }
}
```
