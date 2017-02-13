## RC.GetInteriorVehicleDataCapabilities
Type
:	Function

Sender
:	SDL

Purpose
:	Obtain vehicle capabilities on available modules controls in available locations

_**Trigger to send:**_   
RSDL sends _RC.GetInteriorVehicleDataCapabilities_ to the vehicle after receiving a valid _GetInteriorVehicleDataCapabilities_ request from remote-control application.
 
_**Back-up:**_   
RSDL has a logic to _read the capabilities from the predefined file_ so that to respond to the application in case _the vehicle fails to respond or responds with error_ to _RC.GetInteriorVehicleDataCapabilities_.

To switch this logic on, the OEM must ensure the following:   
   1.	"InteriorVehicleDataCapabilities.json" file that lists all available locations and available modules must be created (please see "Response" in "JSON message example" below for the expected structure).
   2.	"InteriorVDCapabilitiesFile" parameter of _SmartDeviceLink.ini_ file must contain the path to this file.   
               _Example:_ InteriorVDCapabilitiesFile = ./plugins/InteriorVehicleDataCapabilities.json

In case any of the above 2 steps is omitted, RSDL will:   
•	transfer vehicle's error to the mobile app in case the vehicle responds GetInteriorVehicleDataCapabilities with an error.   
•	respond with GENERIC_ERROR result to the mobile app in case the vehicle does not respond during RSDL's internal timeout for vehicle RPCs ("DefaultTimeout" parameter in _SmartDeviceLink.ini_ file; set to 10 sec by default).


### Request

_**Behavior**_:   
1.	The vehicle must:   
    1.1. Provide the list:   
        a. Of available modules for controlling in the requested zone - in case the request comes with "zone" parameter only.   
        b. Of available zones for controlling with the requested module - in case the request comes with "moduleTypes" parameter only.   
        c. Of available modules for controlling in the available zones - in case the request comes without parameters.   
    1.2. Respond with SUCCESS result (see example "response" and diagram A) during 10 sec after getting _RC.GetInteriorVehicleDataCapabilities_ request.   
2.	The vehicle may:   
    2.1. Respond with   
        a. Either REJECTED resultCode   
        b. Or do not respond at all   
  in order to trigger RSDL reading capabilities from a predefined file (see diagram B) for responding to mobile application. 
  Important: conditions from "Back-up" of "Description" must be satisfied, otherwise RSDL will respond with error to mobile app (see diagram C).


#### Parameters

|Param Name|Type|Mandatory|Additional|Description|
|:---------|:---|:--------|:---------|:----------|
|zone|Common.InteriorZone|false|-|If included, only the corresponding modules able to be controlled by that zone will be sent back. If not included, all modules will be returned regardless of their ability to be controlled by specifc zones.|
|moduleTypes|Common.ModuleType|false|array = true<br>minSize = 1<br>maxSize = 1000|If included, only the corresponding type of modules a will be sent back. If not included, all module types will be returned.|
|appID|Integer|true|-|Internal SDL-assigned Id of the application that requested this RPC.|

### Response

_**Behavior**_: 
The below table lists resultCodes that the vehicle may use to respond:

|Result|Description|Message type-WebSocket|Message type - D-Bus|Message Params|Notes|
|:------|:---------|:---------------------|:-------------------|:-------------|:----|
|Success|SUCCESS The vehicle provides the list of zones and modules per application's request.|JSON response|Regular response|interiorVehicleDataCapabilities code: 0|See [example "response"].|
|Failure|REJECTED The vehicle intends to trigger "read capabilities from file" RSDL's logic.|JSON error message|Regular response|code: 4|Applicable for this RPC result codes. Please see Result Enumeration for all SDL-supported codes. See [example "error message"].|
|Failure|GENERIC_ERROR The unknown issue occurred or other codes are not applicable.|JSON error message|Regular response|code: 22| Applicable for this RPC result codes. Please see Result Enumeration for all SDL-supported codes. See [example "error message"].|

[example "response"]: https://github.com/smartdevicelink/sdl_hmi_integration_guidelines/blob/feature/sdl_rc_functionality/docs/RC/GetInteriorVehicleDataCapabilities/index.md#response
[example "error message"]: https://github.com/smartdevicelink/sdl_hmi_integration_guidelines/blob/feature/sdl_rc_functionality/docs/RC/GetInteriorVehicleDataCapabilities/index.md#ExampleError


#### Parameters
|Param Name|Type|Mandatory|Additional|Description|
|:---------|:---|:--------|:---------|:----------|
|interiorVehicleDataCapabilities|Common.ModuleDescription|true|array = true<br>minSize = 1<br>maxSize = 1000|Capabilities of the vehicle: which module is available at which location.|


### Sequence Diagrams   

A. RSDL transfers vehcile's successful response to the mobile application
![RSDL](./assets/2.RSDL%20transfers%20vehcile's%20successful%20response%20to%20the%20mobile.png)  

B. RSDL reads capabilities from file in case of erroneous response or non-response from the vehicle 
![RSDL](.assets/2.RSDL%20reads%20capabilities%20from%20file%20in%20case%20of%20erroneous%20response%20or%20non-response%20from%20the%20vehicle.png)

C. RSDL sends erroneous response to the application
![RSDL](./assets/2.RSDL%20sends%20erroneous%20response%20to%20the%20application.png)


### Example Response

```json
{
     "id" : 64,
     "jsonrpc" : "2.0",
     "method" : "RC.GetInteriorVehicleDataCapabilities",
     “params” :
     {
      "zone" :
      {               
                  "col" : “0”,
                  "row" : "1",
                  "level" : "0",
                  "colspan" : "2",
                  "rowspan" : "2",
                  "levelspan" : "0"
      }
     }
}
```
### Example Request
```json
{
     "id" : 64,
     "jsonrpc" : "2.0",
     "result" :
     {
      "interiorVehicleDataCapabilities" :
     [
{
      "moduleZone" :
      {               
                  "col" : “0”,
                  "row" : "1",
                  "level" : "0",
                  "colspan" : "2",
                  "rowspan" : "2",
                  "levelspan" : "0"
      },
     "moduleType" : RADIO
      },
{
      "moduleZone" :
      {               
                  "col" : “0”,
                  "row" : "1",
                  "level" : "0",
                  "colspan" : "2"
```

### Example Error
```json
{
     "id" : 64,
     "jsonrpc" : "2.0",
     "error" :
     {
      "code" : 4,
      "message" : "The request is rejected",
      "data" :
      {
                 "method" : "RC.GetInteriorVehicleDataCapabilities"
      }
     }
}
```
