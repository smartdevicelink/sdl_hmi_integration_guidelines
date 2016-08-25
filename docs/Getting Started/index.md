# Getting Started

## Component Readiness Confirmation

The HMI must register each component which can communicate with SDL using the following format

```javascript
var JSONMessage = {
            "jsonrpc": "2.0",
            "id": -1,
            "method": "MB.registerComponent",
            "params": {
                "componentName": "UI"
            }
        };
```

The possible componentNames are `UI`, `Buttons`, `BasicCommunication`, `VR`, `TTS`, `Navigation`, and `VehicleInfo`

Once the components are registered, the HMI must notify sdl that it is ready to begin further communication using the [BasicCommunication.OnReady][../basiccommunication/onready] notification.

Upon receipt of the OnReady notification, SDL will begin checking the availablility of the different HMI components via a chain a requests:

  * `UI.IsReady` - The display availability
  * `VR.IsReady` - The voice recognition module availability
  * `TTS.IsReady` - The Text-To-Speech module availability
  * `Navigation.IsReady` - Navigation engine availability
  * `VehicleInfo.IsReady` - Indicates whether vehicle information can be collected and provided.
 
## Registering for Notifications
The HMI must also register for notifications individually using the following RPC format

```javascript
var obj = {
            "jsonrpc": "2.0",
            "id": -1,
            "method": "MB.subscribeTo",
            "params": {
                "propertyName": notificationName
            }
        }
```

Where propertyName is the name of the notification, such as `Buttons.OnButtonSubscription`

!!! must

The HMI must register its components, send the OnReady notification, respond to each of the IsReady RPCs, and register for the notifications it would like to receive.

!!!

!!! info

If the response to any of the component `IsReady` requests contains `{"available": false}`, SDL will no longer communicate with that component.

!!!


### IsReady Sequence Diagram

!!! note

In the case of a WebSocket connection, the RPCs to each of the components is sent within each separate WebSocket connection.

!!!

|||
IsReady Sequence
![IsReady Sequence](./assets/IsReadySequence.png)
|||
