## GetActiveServiceConsent

Type
: Function

Sender
: SDL

Purpose
: Request user consent to activate an app service

### Request

!!! MUST
1. Prompt user to activate service with `serviceID`
2. Respond with the result from the user in the `activate` parameter
!!!

#### Parameters

|Name|Type|Mandatory|Additional|
|:---|:---|:--------|:---------|
|serviceID|String|true||

### Response

#### Parameters

|Name|Type|Mandatory|Additional|
|:---|:---|:--------|:---------|
|activate|Boolean|true||

### Sequence Diagrams
|||
GetActiveServiceConsent (user accepts prompt)
![GetActiveServiceConsent](./assets/GetActiveServiceConsent_Allow.png)
|||

|||
GetActiveServiceConsent (user rejects prompt)
![GetActiveServiceConsent](./assets/GetActiveServiceConsent_Reject.png)
|||

### JSON Message Examples

#### Example Request

```json
{
   "id": 1000,
   "jsonrpc": "2.0",
   "method": "AppService.GetActiveServiceConsent",
   "params": {
      "serviceID": "service_id"
   }
}
```

#### Example Response

```json
{
   "id" : 1000,
   "jsonrpc" : "2.0",
   "result" : {
      "activate" : true,
      "code" : 0,
      "method" : "AppService.GetActiveServiceConsent"
   }
}
```

#### Example Error

```json
{
   "id" : 1000,
   "jsonrpc" : "2.0",
   "error" : {
      "code" : 13,
      "message" : "No known service with given ID",
      "data" : {
          "method" : "AppService.GetActiveServiceConsent"
      }
   }
}
```