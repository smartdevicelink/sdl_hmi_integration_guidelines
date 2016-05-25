## OnLanguageChange

Type
: Notification

Sender
: HMI

Purpose
: Inform SDL that the language of the VR engine has changed.

### Notification

#### Parameters

|Name|Type|Mandatory|Additional|
|:---|:---|:--------|:---------|
|language|[Common.Language](../../Common/Enums/index.md#language)|true||

### Sequence Diagrams
|||
OnLanguageChange
![OnLanguageChange](./assets/OnLanguageChange.png)
|||

#### JSON Example Notification
```json
{
  "jsonrpc" : "2.0",
  "method" : "VR.OnLanguageChange",
  "params" :
  {
    "language" : "IT-IT"
  }
}
```
