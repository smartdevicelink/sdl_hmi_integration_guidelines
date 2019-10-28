## DecryptCertificate

Type
: Function

Sender
: SDL

Purpose
: To decrypt the certificate received via the updated policy table

### Request

#### Parameters

|Name|Type|Mandatory|Additional|Description|
|:---|:---|:--------|:---------|:----------|
|fileName|String|true|minlength: 1<br>maxlength: 255|The path to the file with the encrypted certificate from the PolicyTable|

### Response

#### Parameters

This RPC has no additional parameter requirements

### Example Request

```json
{
  "id": 35,
  "jsonrpc": "2.0",
  "method": "BasicCommunication.DecryptCertificate",
  "params": {
    "fileName": "/home/user/sdl_build/bin/storage/certificate"
  }
}
```

### Example Response

```json
{
  "result": {
    "method": "BasicCommunication.DecryptCertificate",
    "code": 0
  },
  "id": 35,
  "jsonrpc": "2.0"
}
```

### Example Error

```json
{
  "error": {
    "code": 4,
    "message": "Cert is not decrypted",
    "data": {
      "method": "BasicCommunication.DecryptCertificate"
    }
  },
  "id": 42,
  "jsonrpc": "2.0"
}
```