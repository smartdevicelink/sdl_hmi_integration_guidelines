## OnLanguageChange

Type
: Notification

Sender
: HMI

Purpose
: Inform SDL that the language of the <abbr title="Voice Recognition">VR</abbr> engine has changed.

### Notification

#### Parameters

|Name|Type|Mandatory|Additional|
|:---|:---|:--------|:---------|
|language|[Common.Language](../../common/enums/#language)|true||

### Sequence Diagrams

|||
OnLanguageChange  
![OnLanguageChange](./assets/OnLanguageChange.png)
|||

### JSON Message Examples

#### Example Notification

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
