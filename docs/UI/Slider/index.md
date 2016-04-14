## Slider


### Request

#### Parameters

|Name|Type|Mandatory|Additional|Description|
|:---|:---|:--------|:---------|:----------|
|numTicks|Integer|true|minvalue: 2<br>maxvalue: 26||
|position|Integer|true|minvalue: 1<br>maxvalue: 26||
|sliderHeader|String|true|maxlength: 500||
|sliderFooter|String|false|array: true<br>minsize: 1<br>maxsize: 26<br>maxlength: 500||
|timeout|Integer|true|minvalue: 1000<br>maxvalue: 65535||
|appID|Integer|true|||

### Response

#### Parameters

|Name|Type|Mandatory|Additional|Description|
|:---|:---|:--------|:---------|:----------|
|sliderPosition|Integer|false|minvalue: 1<br>maxvalue: 26||
