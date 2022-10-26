## OnExitApplication

Type
: Notification

Sender
: HMI

Purpose
: Inform SDL that an application must be unregistered or put into the NONE HMI state.

!!! MUST

  1. Provide the possibility for the user to exit any of the registered applications.
  2. Track if an application is active or running in the background, and complies with the driver distraction rules of the system.
  3. Track that the transport type that corresponds to the application running. For example, navigation applications are not allowed to be run over a bluetooth connection.
  4. Ignore all SDL RPCs related to an application that are defined as prohibited for a specific transport type.
  5. Track the application performance issues such as high CPU load or memory constraint warnings.
  6. Send `OnExitApplication` notification to SDL if an application conflicts with any of the rules above (i.e. Users requests to exit, driver distraction rules violated, navigation app connected over bluetooth, or the application has performance issues).

!!!

!!! MAY

The HMI may switch layouts or views according to the workflow after deactivation of an application.

!!!

!!! NOTE

  * Information about the application (name, appID, etc) is provided by SDL via [BC.UpdateAppList](../updateapplist) or [BC.OnAppRegistered](../onappregistered).
  * SDL ignores all invalid notifications which come from the HMI (Invalid JSON, invalid data types/bounds, etc).
  * If the HMI sends ApplicationExitReason `CLOSE_CLOUD_CONNECTION`
    * The application will be unregistered.
    * A [BasicCommunication.UpdateDeviceList](../updatedevicelist) (with the closed application) will be sent by SDL.
    * The closed application will have a cloudConnectionStatus of `NOT_CONNECTED`
  * If the HMI sends ApplicationExitReason `RESOURCE_CONSTRAINT` for the application with `AppHMIType` = `WEB_VIEW`
    * SDL should unregister the application allowing the HMI to close this application.

  
!!!

### Notification

#### Parameters

|Name|Type|Mandatory|Additional|
|:---|:---|:--------|:---------|
|reason|[Common.ApplicationExitReason](../../common/enums/#applicationexitreason)|true||
|appID|Integer|true||

### Sequence Diagrams

|||
User Exits Application
![OnExitApplication](./assets/OnExitApplicationUser.png)
|||

|||
Application Not Authorized
![OnExitApplication](./assets/OnExitApplicationUnauth.png)
|||

### JSON Message Examples

#### Example Notification

```json
{
  "jsonrpc" : "2.0",
  "method" : "BasicCommunication.OnExitApplication",
  "params" :
  {
    "appID" : 65544,
    "reason" : "USER_EXIT"
  }
}
```
