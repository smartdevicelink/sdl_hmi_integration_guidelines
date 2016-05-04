## OnExitApplication


### Notification

#### Parameters

|Name|Type|Mandatory|Additional|Description|
|:---|:---|:--------|:---------|:----------|
|reason|Common.ApplicationToNONEReason|true|||
|appID|Integer|true|||

#### ApplicationToNONEReason

|Name|Value|
|:---|:----|
|DRIVER_DISTRACTION_VIOLATION|0|
|USER_EXIT|1|

### Sequence Diagrams
|||
User Exits Application
![OnExitApplication](./assets/OnExitApplicationUser.png)
|||
|||
Application Not Authorized
![OnExitApplication](./assets/OnExitApplicationUnauth.png)
|||

#### JSON Example Notification
```json

```
