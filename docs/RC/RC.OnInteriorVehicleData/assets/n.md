## RC.
Type
:	Function

Sender
:	SDL

Purpose
:	

_**Trigger to send:**_   


_**Back-up:**_   


### Request

_**Behavior**_:   


#### Parameters

|Param Name|Type|Mandatory|Additional|Description|
|:---------|:---|:--------|:---------|:----------|

### Response

_**Behavior**_: 
The below table lists resultCodes that the vehicle may use to respond:

|Result|Description|Message type-WebSocket|Message type - D-Bus|Message Params|Notes|
|:------|:---------|:---------------------|:-------------------|:-------------|:----|
|Success|SUCCESS |JSON response|Regular response|interiorVehicleDataCapabilities code: 0|See [example "response"].|
|Failure|REJECTED |JSON error message|Regular response|code: 4|Applicable for this RPC result codes. Please see Result Enumeration for all SDL-supported codes. See [example "error message"].|
|Failure|GENERIC_ERROR |JSON error message|Regular response|code: 22| Applicable for this RPC result codes. Please see Result Enumeration for all SDL-supported codes. See [example "error message"].|


#### Parameters
|Param Name|Type|Mandatory|Additional|Description|
|:---------|:---|:--------|:---------|:----------|


### Sequence Diagrams   

A. n
![DL](./assets/le.png)  

B. le 
![R](.assets/cle.png)


### Example Response

```json

```
### Example Request
```json

```

### Example Error
```json

```
