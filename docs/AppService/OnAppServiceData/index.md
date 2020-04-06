## OnAppServiceData

Type
: Notification

Sender
: HMI / SDL

Purpose
: Sent by the app service provider when its service data is updated. Broadcast by SDL to all consumers subscribed to this service type.

!!! note

* **HMI->SDL** if HMI App Service Provider (ASP) is sending updated service data  
* **SDL->HMI** if HMI App Service Consumer (ASC) is receiving updated service data

!!!

### Notification

#### Parameters

|Name|Type|Mandatory|Additional|
|:---|:---|:--------|:---------|
|serviceData|[Common.AppServiceData](../../common/structs/#appservicedata)|true||

### Sequence Diagrams

|||
OnAppServiceData (HMI Provider)
![OnAppServiceData_HMI_ASP](./assets/OnAppServiceData_HMI_ASP.png)
|||

|||
OnAppServiceData (HMI Consumer)
![OnAppServiceData_HMI_ASC](./assets/OnAppServiceData_HMI_ASC.png)
|||

### JSON Message Examples

#### Example Notification

```json
{
  "jsonrpc": "2.0",
  "method": "AppService.OnAppServiceData",
  "params": {
    "serviceData": {
      "mediaServiceData": {
        "isExplicit": false,
        "mediaAlbum": "Book Name",
        "mediaArtist": "Author name",
        "mediaTitle": "Chapter name",
        "mediaType": "AUDIOBOOK",
        "queueCurrentTrackNumber": 12,
        "queuePlaybackDuration": 4000,
        "queuePlaybackProgress": 2200,
        "queueTotalTrackCount": 25,
        "trackPlaybackDuration": 300,
        "trackPlaybackProgress": 200
      },
      "serviceID": "9c6697b90f561cc599af19f81e9cf68a6848d6df1cdd63820d75ebfd7c727a20",
      "serviceType": "MEDIA"
    }
  }
}
```
