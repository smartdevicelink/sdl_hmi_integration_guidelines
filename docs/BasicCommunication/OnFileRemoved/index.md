## OnFileRemoved

Type
: Notification

Sender
: SDL

Purpose
: Inform the HMI that a file has been removed from a shared folder by an application.


### Notification

#### Parameters

|Name|Type|Mandatory|Additional|
|:---|:---|:--------|:---------|
|fileName|String|true|minlength: 1<br>maxlength: 30|
|fileType|[Common.FileType](../../Common/Enums/index.md#filetype)|true||
|appID|Integer|true||

### Sequence Diagrams
|||
File Removed from Head Unit
![OnFileRemoved](./assets/OnFileRemoved.png)
|||

#### JSON Example Notification
```json
{
	"jsonrpc" : "2.0",
	"method" : "BasicCommunication.OnFileRemoved"
     "params" :
	{
      "appID" : 31780,
"fileName" : "/fs/rwdata/storage/sdl/Emergency584421907/syncFileName",
      "fileType" : "GRAPHIC_BMP"      
	}

}
```
