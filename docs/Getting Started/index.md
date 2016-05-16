# Getting Started
## Component Readiness Confirmation
To start communication with SDL, the HMI must notify about its ready via the `BasicCommunication.OnReady` notification.

Upon receipt of the OnReady notification, SDL will begin checking the available of the different HMI components via a chain a requests:

  * `UI.IsReady` - The display availability
  * `VR.IsReady` - The voice recognition module availability
  * `TTS.IsReady` - The Text-To-Speech module availability
  * `Navigation.IsReady` - Navigation engine availability
  * `VehicleInfo.IsReady` - Indicates whether vehicle information can be collected and provided.

!!! must

The HMI must respond to each of the above RPCs.

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
