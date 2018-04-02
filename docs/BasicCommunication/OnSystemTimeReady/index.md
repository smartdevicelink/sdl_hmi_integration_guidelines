## OnSystemTimeReady

Type
: Notification

Sender
: HMI

Purpose
: Inform SDL about readiness to provide system time

!!! must

The HMI must send BC.OnSystemTimeReady to SDL due to new ignition cycle in order to notify SDL about readiness to provide system time.
!!!

### Notification

#### Parameters

|Name|Type|Mandatory|Additional|
|:---|:---|:--------|:---------|

### Sequence Diagrams
|||
OnSystemTimeReady
![OnSystemTimeReady](assets/OnSystemTimeReady_Ign_On.png)
|||

#### JSON Example Notification  

```
{
	"jsonrpc" : "2.0",
	"method" : "BasicCommunication.OnSystemTimeReady"
}
```