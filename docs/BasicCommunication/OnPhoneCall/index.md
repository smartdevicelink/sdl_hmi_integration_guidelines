## OnPhoneCall


### Notification

#### Parameters

|Name|Type|Mandatory|Additional|Description|
|:---|:---|:--------|:---------|:----------|
|isActive|Boolean|true|||

### Sequence Diagrams
|||
Phone Call
![OnPhoneCall](./assets/OnPhoneCall.png)
|||

#### JSON Example Notification
```json
{
	"jsonrpc" : "2.0",
	"method" : "BasicCommunication.OnPhoneCall"
     "params" :
	{
       "isActive": true
     }
}
```
