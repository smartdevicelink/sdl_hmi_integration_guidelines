## OnStatusUpdate

Type
: Notification

Sender
: SDL

Purpose
: Inform the HMI about the status of a Policy Table Update (PTU).

### Notification

!!! may


!!!

!!! note

SDL operates with the following PTU statuses:

!!!

#### Parameters

|Name|Type|Mandatory|Additional|
|:---|:---|:--------|:---------|
|status|[Common.UpdateResult](../../common/enums/index.md#updateresult)|true||

#### JSON Example Notification
```json
{
  "jsonrpc" : "2.0",
  "method" : "SDL.OnStatusUpdate",
  "params" :  
  {
    "status" : "UPDATE_NEEDED"
  }
}
```

### Sequence Diagrams
|||
|||
