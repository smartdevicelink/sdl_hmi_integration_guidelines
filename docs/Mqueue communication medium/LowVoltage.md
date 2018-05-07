## Low Voltage  

Type
: Signal

Sender
: HMI

Purpose
: To suspended SDL's services due to a low voltage event

### Description  
'LowVoltage' event occurs on HMI when battery voltage hits below a certain predefined threshold set by the system.  
 In case of such an event, the EMMC is turned off and all read/write operations are unavailable. After the voltage level is restored all operations are resumed.

!!! MUST   

1. Send "LOW_VOLTAGE" message via mqueue to SDL when 'LowVoltage' event occurs
2. Send "WAKE_UP" message via mqueue to SDL when the voltage recovers
3. Send "IGNITION_OFF" message via mqueue to SDL when 

!!!

!!! NOTE 
* SDL ignores all the requests from mobile applications without providing any kind of response
* SDL ignores all responses and messages from HMI except messages for "WAKE_UP" or "IGNITION_OFF"  
* All transports are unavailable for SDL
* SDL persists resumption related data stored before receiving a "LOW_VOLTAGE" message  
* SDL resumes its regular work after receiving a "WAKE_UP" message  
* SDL must start up correctly in the next ignition cycle after it was powered off in low voltage state

#### Parameters
**Message queue channel between HMI and SDL**

Mqueue name can be specified in smartdevicelink.ini file:

```
[MAIN] 
; Message queue name used by SDL for handling LOW_VOLTAGE functionality
SDLMessageQueueName = /SDLMQ
```  

**Message queue signals value**  

|Signal name|Value(string)|
|:---|:---| 
|LOW_VOLTAGE|"LOW_VOLTAGE"|
|WAKE_UP|"WAKE_UP"|
|IGNITION_OFF|"IGNITION_OFF"|

### Sequence Diagrams  

|||
Low Voltage  
![Low Voltage](./assets/low_voltage.png)  
|||