## OnResetTimeout

Type
: Notification

Sender
: HMI

Purpose
: Inform SDL about RPC instance for which timeout needs to be reset 

### Notification
HMI can send this notification used by functions in all interfaces to notify that timeout needs to be reset.

!!! must
  * send OnResetTimeout to SDL in case HMI needs more time for processing a request from mobile application
  * fine tune the wait time per method call as needed
  * control number of reset timeouts and duration of each reset timeout for endless or finite method timeout

!!!

HMI can send OnResetTimeout to inform SDL that the timeout of **UI RPC** is reset by definite User's actions.

!!! must
  * send OnResetTimeout to SDL upon every Users keypress processing UI.PerfromInteraction(layoutMode:KEYBOARD) request 
  * send OnResetTimeout to SDL upon Users actions over the message (e.g. scrolling) processing UI.ScrollableMessage request
  * send OnResetTimeout to SDL upon KEEP_CONTEXT soft button (defined within UI.ScrollableMessage RPC) press
!!!

HMI can send OnResetTimeout to reset the timeout for some **TTS RPC** running on HMI (e.g.Speak).  
SDL's default timeout for any response from HMI is 10 seconds. So it needs to know if some TTS RPC is still running on HMI to predict sending wrong response by timeout. OnResetTimeout notifies SDL to reset the timeout for some TTS RPC running on HMI (e.g.Speak).

!!! must
  * send OnResetTimeout to SDL in case HMI speak event lasts longer than 10 seconds
!!!

_Note: Currently there is no version negotiation between HMI and Core, so older HMI implementations will not work with this new version of Core._

#### Parameters
|Name|Type|Mandatory|Additional|
|:---|:---|:--------|:---------|
|requestID|Integer|true|minvalue="0" maxvalue="65535"|
|methodName|String|true||
|resetPeriod|Integer|false| minvalue="0" maxvalue="1000000" |

### Sequence Diagrams

#### JSON Example Notification
```json
{
  "jsonrpc" : "2.0",
  "method" : "BC.OnResetTimeout",
     "params" :
  {
    "requestID" : 123,
    "methodName" : "TTS.Speak",
    "resetPeriod" : 10000
  }
}
```