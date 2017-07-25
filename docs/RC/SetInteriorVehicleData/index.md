## SetInteriorVehicleData

Type
: Function

Sender
: SDL

Purpose
: Set RC module settings

RC.SetInteriorvehicledata represents a request from an application to change settings of requested RC module. This RPC can be sent to the HMI for an application that is registered with REMOTE_CONTROL appHMIType and in one of the following states: FULL, LIMITTED, BACKGROUND. Module signed by the application in such reques has to be available on HMI and allowed for control change settings

!!! must

  1. Modules sent by application must be available on HMI
  2. Access to control module settings is defined by access mode entered by user on HMI
  3. Module settings can be changed for settable parameters only
  4. Requested module items have to be available for such module on HMI


!!!

### Request

#### Parameters

|Name|Type|Mandatory|Additional|Description|
|:---|:---|:--------|:---------|:---------|
|moduleData|Common.ModuleData|true||The module type and data to set|
|appID|Integer|true||Internal SDL-assigned ID of the related application|

### Response

#### Parameters

|Name|Type|Mandatory|Additional|Description|
|:---|:---|:--------|:---------|:---------|
|moduleData|Common.ModuleData|true|||


### Example Request

### Example Response

### Example Error
