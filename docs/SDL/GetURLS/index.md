## GetURLS

Type
: Function

Sender
: HMI

Purpose
: Retrieve the destination URL(s) from Local Policy Table

### Request

!!! must

For Proprietary PTU flow:  
1. Send `SDL.GetURLS` after SDL-initiated  [BC.PolicyUpdate](../../BasicCommunication/PolicyUpdate/index.md#PolicyUpdate) with service type  **7**
* Use the received URL(s) in the next  [BC.OnSystemRequest](../../BasicCommunication/OnSystemRequest/index.md#OnSystemRequest)

!!!

!!! may

Request the URL(s) for any known service type that exists in Local PT at any time if required per internal flows.

!!!

!!! note

1. `SDL.GetURLS` dependencies:
   * SDL responds to `SDL.GetURLS` _only in case_ it's built with ``"-DEXTENDED_POLICY: ON"`` flag.   
* URLs storage in Policy Table: `"endpoints"` section ([example](https://github.com/smartdevicelink/sdl_core/blob/master/src/appMain/sdl_preloaded_pt.json#L16))
* SDL chooses the applications for taking part in PTU among registered ones and provides `appID` + `url` pairs in response  
* In case no applications are currently registered, SDL will return `url` only

!!!

#### Parameters

|Name|Type|Mandatory|Additional|
|:---|:---|:--------|:---------|
|service|Integer|true|minvalue: 0<br>maxvalue: 100|

### Response

#### Parameters

|Name|Type|Mandatory|Additional|
|:---|:---|:--------|:---------|
|urls|[Common.ServiceInfo]|false|array: true<br>minsize: 1<br>maxsize: 100|
[Common.ServiceInfo]: https://github.com/KhrystynaDubovyk/sdl_hmi_integration_guidelines/blob/dextended_policy_proprietary/docs/Common/Structs/index.md#serviceinfo 
### Example Request

```json
{
	"id" : 176,
	"jsonrpc" : "2.0",
	"method" : "SDL.GetURLS",
	"params" :
	{
		"service" : 7
	}
}
```
### Example Response

```json
{
	"id" : 176,
	"jsonrpc" : "2.0",
	"result" :
	{
		"urls" :
		[
         {
            "url" : "https://policies.smartdevicelink.com/api/1/policies",
            "appID" : 65782
         }
		],
		"code" : 0,
		"method" : "SDL.GetURLS"
	}
}
```

### Example Error

```json
{
	"id" : 176,
	"jsonrpc" : "2.0",
	"error" :
	{
		"code" : 11,
		"message" : "Invalid data",
		"data" :
		{
			"method" : "SDL.GetURLS"
		}
	}
}
```

### Sequence Diagrams

|||
BC.PolicyUpdate in "Proprietary" Policy Table Update Flow
![Proprietary PTU](./assets/GetURLS_in_Proprietary_PTU_flow.png)
|||
