## Structs

### ImageResolution

|Name|Type|Mandatory|Additional|Description|
|:---|:---|:--------|:---------|:----------|
|resolutionWidth|Integer|true|minvalue: 1<br>maxvalue: 10000||
|resolutionHeight|Integer|true|minvalue: 1<br>maxvalue: 10000||

### UserFriendlyMessage

|Name|Type|Mandatory|Additional|Description|
|:---|:---|:--------|:---------|:----------|
|messageCode|String|true|||
|ttsString|String|false|||
|label|String|false|||
|line1|String|false|||
|line2|String|false|||
|textBody|String|false|||

### HMICapabilities

|Name|Type|Mandatory|Additional|Description|
|:---|:---|:--------|:---------|:----------|
|navigation|Boolean|false||Availability of build in Nav. True: Available, False: Not Available|
|phoneCall|Boolean|false||Availability of build in phone. True: Available, False: Not Available|
|videoStreaming|Boolean|false||Availability of built-in video streaming. True: Available, False: Not Available|

### NavigationCapability

|Name|Type|Mandatory|Additional|Description|
|:---|:---|:--------|:---------|:----------|
|sendLocationEnabled|Boolean|false||If the module has the ability to add locations to the onboard nav|
|getWayPointsEnabled|Boolean|false||If the module has the ability to return way points from onboard nav|

### PhoneCapability

|Name|Type|Mandatory|Additional|Description|
|:---|:---|:--------|:---------|:----------|
|dialNumberEnabled|Boolean|false||If the module has the ability to perform dial number|

### VideoStreamingCapability

|Name|Type|Mandatory|Additional|Description|
|:---|:---|:--------|:---------|:----------|
|preferredResolution|Common.ImageResolution|false| |The preferred resolution of a video stream for decoding and rendering on HMI.|
|maxBitrate|Integer|false|minvalue: 0<br>maxvalue: 2147483647|The maximum bitrate of video stream that is supported, in Kbps.|
|supportedFormats|Common.VideoStreamingFormat|false|array: true|Detailed information on each format supported by this system, in its preferred order.|
|hapticSpatialDataSupported|Boolean|false| |True if the system can utilize the haptic spatial data from the source being streamed.|
|diagonalScreenSize|Float|false|minvalue: 0|The diagonal screen size in inches.|
|pixelPerInch|Float|false|minvalue: 0|PPI is the diagonal resolution in pixels divided by the diagonal screen size in inches.|
|scale|Float|false|minvalue: 1<br>maxvalue: 10|The scaling factor the app should use to change the size of the projecting view.|

### DriverDistractionCapability
|Name|Type|Mandatory|Additional|Description|
|:---|:---|:--------|:---------|:----------|
|menuLength|Integer|false||The number of items allowed in a Choice Set or Command menu while the driver is distracted|
|subMenuDepth|Integer|false|minvalue: 1|The depth of submenus allowed when the driver is distracted. e.g. 3 == top level menu -> submenu -> submenu; 1 == top level menu only|


### SystemCapabilities

|Name|Type|Mandatory|Additional|Description|
|:---|:---|:--------|:---------|:----------|
|navigationCapability|Common.NavigationCapability|false|||
|phoneCapability|Common.PhoneCapability|false|||
|videoStreamingCapability|Common.VideoStreamingCapability|false|||
|driverDistractionCapability|Common.DriverDistractionCapability|false||Describes capabilities when the driver is distracted|

### MenuParams

|Name|Type|Mandatory|Additional|Description|
|:---|:---|:--------|:---------|:----------|
|parentID|Integer|false|minvalue: 0<br>maxvalue: 2000000000||
|position|Integer|false|minvalue: 0<br>maxvalue: 1000||
|menuName|String|true|maxlength: 500||
|secondaryText|String|false|maxlength: 500||
|tertiaryText|String|false|maxlength: 500||

### TireStatus

|Name|Type|Mandatory|Additional|Description|
|:---|:---|:--------|:---------|:----------|
|pressureTelltale|[Common.WarningLightStatus](../enums/#warninglightstatus)|false|||
|leftFront|Common.SingleTireStatus|false|||
|rightFront|Common.SingleTireStatus|false|||
|leftRear|Common.SingleTireStatus|false|||
|rightRear|Common.SingleTireStatus|false|||
|innerLeftRear|Common.SingleTireStatus|false|||
|innerRightRear|Common.SingleTireStatus|false|||

### ECallInfo

|Name|Type|Mandatory|Additional|Description|
|:---|:---|:--------|:---------|:----------|
|eCallNotificationStatus|[Common.VehicleDataNotificationStatus](../enums/#vehicledatanotificationstatus)|true|||
|auxECallNotificationStatus|[Common.VehicleDataNotificationStatus](../enums/#vehicledatanotificationstatus)|true|||
|eCallConfirmationStatus|[Common.ECallConfirmationStatus](../enums/#ecallconfirmationstatus)|true|||

### DIDResult

|Name|Type|Mandatory|Additional|Description|
|:---|:---|:--------|:---------|:----------|
|resultCode|[Common.VehicleDataResultCode](../enums/#vehicledataresultcode)|true|||
|didLocation|Integer|true|minvalue: 0<br>maxvalue: 65535||
|data|String|false|maxlength: 5000||

### TTSChunk

|Name|Type|Mandatory|Additional|Description|
|:---|:---|:--------|:---------|:----------|
|text|String|true|maxlength: 500|The text/phonemes to be spoken or the name of an audio file to play|
|type|[Common.SpeechCapabilities](../enums/#speechcapabilities)|true||Describes how to interpret the text field (as plain text, a file name, etc.)|

### TextField

|Name|Type|Mandatory|Additional|Description|
|:---|:---|:--------|:---------|:----------|
|name|[Common.TextFieldName](../enums/#textfieldname)|true|||
|characterSet|[Common.CharacterSet](../enums/#characterset)|true|||
|width|Integer|true|minvalue: 1<br>maxvalue: 500||
|rows|Integer|true|minvalue: 1<br>maxvalue: 8||

### TouchCoord

|Name|Type|Mandatory|Additional|Description|
|:---|:---|:--------|:---------|:----------|
|x|Integer|true|minvalue: 0<br>maxvalue: 10000||
|y|Integer|true|minvalue: 0<br>maxvalue: 10000||

### AudioPassThruCapabilities

|Name|Type|Mandatory|Additional|Description|
|:---|:---|:--------|:---------|:----------|
|samplingRate|[Common.SamplingRate](../enums/#samplingrate)|true|||
|bitsPerSample|[Common.BitsPerSample](../enums/#bitspersample)|true|||
|audioType|[Common.AudioType](../enums/#audiotype)|true|||

### ServiceInfo

|Name|Type|Mandatory|Additional|Description|
|:---|:---|:--------|:---------|:----------|
|url|String|true||Get URL based on service type.|
|appID|Integer|false||ID of application that requested this RPC.|

### HeadLampStatus

|Name|Type|Mandatory|Additional|Description|
|:---|:---|:--------|:---------|:----------|
|lowBeamsOn|Boolean|true|||
|highBeamsOn|Boolean|true|||
|ambientLightSensorStatus|[Common.AmbientLightStatus](../enums/#ambientlightstatus)|true|||

### ClusterModeStatus

|Name|Type|Mandatory|Additional|Description|
|:---|:---|:--------|:---------|:----------|
|powerModeActive|Boolean|true|||
|powerModeQualificationStatus|[Common.PowerModeQualificationStatus](../enums/#powermodequalificationstatus)|true|||
|carModeStatus|[Common.CarModeStatus](../enums/#carmodestatus)|true|||
|powerModeStatus|[Common.PowerModeStatus](../enums/#powermodestatus)|true|||

### KeyboardProperties

|Name|Type|Mandatory|Additional|Description|
|:---|:---|:--------|:---------|:----------|
|language|[Common.Language](../enums/#language)|false|||
|keyboardLayout|[Common.KeyboardLayout](../enums/#keyboardlayout)|false|||
|keypressMode|[Common.KeypressMode](../enums/#keypressmode)|false|||
|limitedCharacterList|String|false|array: true<br>minsize: 1<br>maxsize: 100<br>maxlength: 1||
|autoCompleteList|String|false|array: true<br>minsize: 0<br>maxsize: 100<br>maxlength: 1000||

### Choice

|Name|Type|Mandatory|Additional|Description|
|:---|:---|:--------|:---------|:----------|
|choiceID|Integer|true|minvalue: 0<br>maxvalue: 65535||
|menuName|String|false|maxlength: 500||
|image|Common.Image|false|||
|secondaryText|String|false|maxlength: 500||
|tertiaryText|String|false|maxlength: 500||
|secondaryImage|Common.Image|false|||

### DeviceStatus

|Name|Type|Mandatory|Additional|Description|
|:---|:---|:--------|:---------|:----------|
|voiceRecOn|Boolean|false|||
|btIconOn|Boolean|false|||
|callActive|Boolean|false|||
|phoneRoaming|Boolean|false|||
|textMsgAvailable|Boolean|false|||
|battLevelStatus|[Common.DeviceLevelStatus](../enums/#devicelevelstatus)|false|||
|stereoAudioOutputMuted|Boolean|false|||
|monoAudioOutputMuted|Boolean|false|||
|signalLevelStatus|[Common.DeviceLevelStatus](../enums/#devicelevelstatus)|false|||
|primaryAudioSource|[Common.PrimaryAudioSource](../enums/#primaryaudiosource)|false|||
|eCallEventActive|Boolean|false|||

### GPSData

|Name|Type|Mandatory|Additional|Description|
|:---|:---|:--------|:---------|:----------|
|longitudeDegrees|Float|true|minvalue: -180<br>maxvalue: 180||
|latitudeDegrees|Float|true|minvalue: -90<br>maxvalue: 90||
|utcYear|Integer|false|minvalue: 2010<br>maxvalue: 2100||
|utcMonth|Integer|false|minvalue: 1<br>maxvalue: 12||
|utcDay|Integer|false|minvalue: 1<br>maxvalue: 31||
|utcHours|Integer|false|minvalue: 0<br>maxvalue: 23||
|utcMinutes|Integer|false|minvalue: 0<br>maxvalue: 59||
|utcSeconds|Integer|false|minvalue: 0<br>maxvalue: 59||
|compassDirection|[Common.CompassDirection](../enums/#compassdirection)|false|||
|pdop|Float|false|minvalue: 0<br>maxvalue: 1000||
|hdop|Float|false|minvalue: 0<br>maxvalue: 1000||
|vdop|Float|false|minvalue: 0<br>maxvalue: 1000||
|actual|Boolean|false|||
|satellites|Integer|false|minvalue: 0<br>maxvalue: 31||
|dimension|[Common.Dimension](../enums/#dimension)|false|||
|altitude|Float|false|minvalue: -10000<br>maxvalue: 10000||
|heading|Float|false|minvalue: 0<br>maxvalue: 359.99||
|speed|Float|false|minvalue: 0<br>maxvalue: 500||
|shifted|Boolean|false||True, if <abbr title="Global Positioning System">GPS</abbr> lat/long, time, and altitude have been purposefully shifted (requires a proprietary algorithm to un-shift).<br>False, if the <abbr title="Global Positioning System">GPS</abbr> data is raw and un-shifted.<br>If not provided, then value is assumed False|

### SingleTireStatus

|Name|Type|Mandatory|Additional|Description|
|:---|:---|:--------|:---------|:----------|
|status|[Common.ComponentVolumeStatus](../enums/#componentvolumestatus)|true|||
|tpms|[Common.TPMS](../enums/#tpms)|false||The status of TPMS according to the particular tire.|
|pressure|Float|false|minvalue: 0<br>maxvalue: 2000|The pressure value of the particular tire in kilopascals.|

### SoftButtonCapabilities

|Name|Type|Mandatory|Additional|Description|
|:---|:---|:--------|:---------|:----------|
|shortPressAvailable|Boolean|true||The button supports a short press.<br>Whenever the button is pressed short, onButtonPressed( SHORT) must be invoked.|
|longPressAvailable|Boolean|true||The button supports a LONG press.<br>Whenever the button is pressed long, onButtonPressed( LONG) must be invoked.|
|upDownAvailable|Boolean|true||The button supports "button down" and "button up".<br>Whenever the button is pressed, onButtonEvent( DOWN) must be invoked.<br>Whenever the button is released, onButtonEvent( UP) must be invoked.|
|imageSupported|Boolean|true||Must be true if the button supports referencing a static or dynamic image.|
|textSupported|Boolean|false||The button supports the use of text.<br>If not included, the default value should be considered true that the button will support text.|

### HMIApplication

|Name|Type|Mandatory|Additional|Description|
|:---|:---|:--------|:---------|:----------|
|appName|String|true|maxlength: 100||
|ngnMediaScreenAppName|String|false|maxlength: 100||
|icon|String|false|||
|deviceInfo|Common.DeviceInfo|true|||
|secondaryDeviceInfo|Common.DeviceInfo|false||The ID, serial number, transport type that are acquired through Secondary Transport.|
|policyAppID|String|true|minlength: 1<br>maxlength: 50||
|ttsName|Common.TTSChunk|false|array: true<br>minsize: 1<br>maxsize: 100||
|vrSynonyms|String|false|array: true<br>minsize: 1<br>maxsize: 100<br>maxlength: 40||
|appID|Integer|true||Must not interfere with any name of previously registered applications from the same device|
|hmiDisplayLanguageDesired|[Common.Language](../enums/#language)|false|||
|isMediaApplication|Boolean|false|||
|appType|[Common.AppHMIType](../enums/#apphmitype)|false|array: true<br>minsize: 1<br>maxsize: 100||
|greyOut|Boolean|false|||
|requestType|[Common.RequestType](../enums/#requesttype)|false|array: true<br>minsize: 0<br>maxsize: 100||
|requestSubType|String|false|array: true<br>minsize: 0<br>maxsize: 100<br>maxlength: 100|The list of SystemRequest's requestSubTypes allowed by policies for the named application.<br>If the app sends a requestSubType which is not specified in this list, then that request should be rejected.<br>An empty array signifies that any value of requestSubType is allowed for this app. <br> If this parameter is omitted, then a request with any value of requestSubType is now allowed for this app|
|dayColorScheme|Common.TemplateColorScheme|false|||
|nightColorScheme|Common.TemplateColorScheme|false|||
|isCloudApplication|Boolean|false|||
|cloudConnectionStatus|[Common.CloudConnectionStatus](../enums/#cloudconnectionstatus)|false|||

### VehicleType

|Name|Type|Mandatory|Additional|Description|
|:---|:---|:--------|:---------|:----------|
|make|String|false|maxlength: 500||
|model|String|false|maxlength: 500||
|modelYear|String|false|maxlength: 500||
|trim|String|false|maxlength: 500||

### ButtonCapabilities

|Name|Type|Mandatory|Additional|Description|
|:---|:---|:--------|:---------|:----------|
|name|[Common.ButtonName](../enums/#buttonname)|true|||
|shortPressAvailable|Boolean|true|||
|longPressAvailable|Boolean|true|||
|upDownAvailable|Boolean|true|||
|moduleInfo|Common.ModuleInfo|false||Information about a RC module, including its id.|

### VrHelpItem

|Name|Type|Mandatory|Additional|Description|
|:---|:---|:--------|:---------|:----------|
|text|String|true|maxlength: 500||
|image|Common.Image|false|||
|position|Integer|true|minvalue: 1<br>maxvalue: 100||

### BodyInformation

|Name|Type|Mandatory|Additional|Description|
|:---|:---|:--------|:---------|:----------|
|parkBrakeActive|Boolean|true|||
|ignitionStableStatus|[Common.IgnitionStableStatus](../enums/#ignitionstablestatus)|true|||
|ignitionStatus|[Common.IgnitionStatus](../enums/#ignitionstatus)|true|||
|driverDoorAjar|Boolean|false|||
|passengerDoorAjar|Boolean|false|||
|rearLeftDoorAjar|Boolean|false|||
|rearRightDoorAjar|Boolean|false|||

### BeltStatus

|Name|Type|Mandatory|Additional|Description|
|:---|:---|:--------|:---------|:----------|
|driverBeltDeployed|[Common.VehicleDataEventStatus](../enums/#vehicledataeventstatus)|false|||
|passengerBeltDeployed|[Common.VehicleDataEventStatus](../enums/#vehicledataeventstatus)|false|||
|passengerBuckleBelted|[Common.VehicleDataEventStatus](../enums/#vehicledataeventstatus)|false|||
|driverBuckleBelted|[Common.VehicleDataEventStatus](../enums/#vehicledataeventstatus)|false|||
|leftRow2BuckleBelted|[Common.VehicleDataEventStatus](../enums/#vehicledataeventstatus)|false|||
|passengerChildDetected|[Common.VehicleDataEventStatus](../enums/#vehicledataeventstatus)|false|||
|rightRow2BuckleBelted|[Common.VehicleDataEventStatus](../enums/#vehicledataeventstatus)|false|||
|middleRow2BuckleBelted|[Common.VehicleDataEventStatus](../enums/#vehicledataeventstatus)|false|||
|middleRow3BuckleBelted|[Common.VehicleDataEventStatus](../enums/#vehicledataeventstatus)|false|||
|leftRow3BuckleBelted|[Common.VehicleDataEventStatus](../enums/#vehicledataeventstatus)|false|||
|rightRow3BuckleBelted|[Common.VehicleDataEventStatus](../enums/#vehicledataeventstatus)|false|||
|leftRearInflatableBelted|[Common.VehicleDataEventStatus](../enums/#vehicledataeventstatus)|false|||
|rightRearInflatableBelted|[Common.VehicleDataEventStatus](../enums/#vehicledataeventstatus)|false|||
|middleRow1BeltDeployed|[Common.VehicleDataEventStatus](../enums/#vehicledataeventstatus)|false|||
|middleRow1BuckleBelted|[Common.VehicleDataEventStatus](../enums/#vehicledataeventstatus)|false|||

### Turn

|Name|Type|Mandatory|Additional|Description|
|:---|:---|:--------|:---------|:----------|
|navigationText|Common.TextFieldStruct|false|||
|turnIcon|Common.Image|false|||

### EmergencyEvent

|Name|Type|Mandatory|Additional|Description|
|:---|:---|:--------|:---------|:----------|
|emergencyEventType|[Common.EmergencyEventType](../enums/#emergencyeventtype)|true|||
|fuelCutoffStatus|[Common.FuelCutoffStatus](../enums/#fuelcutoffstatus)|true|||
|rolloverEvent|[Common.VehicleDataEventStatus](../enums/#vehicledataeventstatus)|true|||
|maximumChangeVelocity|Integer|true|minvalue: 0<br>maxvalue: 255||
|multipleEvents|[Common.VehicleDataEventStatus](../enums/#vehicledataeventstatus)|true|||

### VehicleDataResult

|Name|Type|Mandatory|Additional|Description|
|:---|:---|:--------|:---------|:----------|
|dataType|[Common.VehicleDataType](../enums/#vehicledatatype)|true|||
|resultCode|[Common.VehicleDataResultCode](../enums/#vehicledataresultcode)|true|||

### PresetBankCapabilities

|Name|Type|Mandatory|Additional|Description|
|:---|:---|:--------|:---------|:----------|
|onScreenPresetsAvailable|Boolean|true|||

### TouchEvent

|Name|Type|Mandatory|Additional|Description|
|:---|:---|:--------|:---------|:----------|
|id|Integer|true|minvalue: 0<br>maxvalue: 9||
|ts|Integer|true|array: true<br>minsize: 1<br>maxsize: 1000<br>minvalue: 0<br>maxvalue: 2147483647||
|c|Common.TouchCoord|true|array: true<br>minsize: 1<br>maxsize: 1000||

### PermissionItem

|Name|Type|Mandatory|Additional|Description|
|:---|:---|:--------|:---------|:----------|
|name|String|true|||
|id|Integer|true|||
|allowed|Boolean|false|||

### TouchEventCapabilities

|Name|Type|Mandatory|Additional|Description|
|:---|:---|:--------|:---------|:----------|
|pressAvailable|Boolean|true|||
|multiTouchAvailable|Boolean|true|||
|doublePressAvailable|Boolean|true|||

### ScreenParams

|Name|Type|Mandatory|Additional|Description|
|:---|:---|:--------|:---------|:----------|
|resolution|Common.ImageResolution|true|||
|touchEventAvailable|Common.TouchEventCapabilities|false|||

### TextFieldStruct

|Name|Type|Mandatory|Additional|Description|
|:---|:---|:--------|:---------|:----------|
|fieldName|[Common.TextFieldName](../enums/#textfieldname)|true||The name of the field for displaying the text.|
|fieldText|String|true|maxlength: 500|The text itself.|
|fieldTypes|[Common.MetadataType](../enums/#metadatatype)|false|minsize: 0<br>maxsize: 5<br>array: true|The type of data contained in the field.|

### DeviceInfo

|Name|Type|Mandatory|Additional|Description|
|:---|:---|:--------|:---------|:----------|
|name|String|true|||
|id|String|true|||
|transportType|[Common.TransportType](../enums/#transporttype)|false|||
|isSDLAllowed|Boolean|false|||

### SoftButton

|Name|Type|Mandatory|Additional|Description|
|:---|:---|:--------|:---------|:----------|
|type|[Common.SoftButtonType](../enums/#softbuttontype)|true|||
|text|String|false|maxlength: 500||
|image|Common.Image|false|||
|isHighlighted|Boolean|false|||
|softButtonID|Integer|true|minvalue: 0<br>maxvalue: 65535||
|systemAction|[Common.SystemAction](../enums/#systemaction)|true|||

### AirbagStatus

|Name|Type|Mandatory|Additional|Description|
|:---|:---|:--------|:---------|:----------|
|driverAirbagDeployed|[Common.VehicleDataEventStatus](../enums/#vehicledataeventstatus)|true|||
|driverSideAirbagDeployed|[Common.VehicleDataEventStatus](../enums/#vehicledataeventstatus)|true|||
|driverCurtainAirbagDeployed|[Common.VehicleDataEventStatus](../enums/#vehicledataeventstatus)|true|||
|passengerAirbagDeployed|[Common.VehicleDataEventStatus](../enums/#vehicledataeventstatus)|true|||
|passengerCurtainAirbagDeployed|[Common.VehicleDataEventStatus](../enums/#vehicledataeventstatus)|true|||
|driverKneeAirbagDeployed|[Common.VehicleDataEventStatus](../enums/#vehicledataeventstatus)|true|||
|passengerSideAirbagDeployed|[Common.VehicleDataEventStatus](../enums/#vehicledataeventstatus)|true|||
|passengerKneeAirbagDeployed|[Common.VehicleDataEventStatus](../enums/#vehicledataeventstatus)|true|||

### RGBColor

|Name|Type|Mandatory|Additional|Description|
|:---|:---|:--------|:---------|:----------|
|red|Integer|true|minvalue: 0<br>maxvalue: 255||
|green|Integer|true|minvalue: 0<br>maxvalue: 255||
|blue|Integer|true|minvalue: 0<br>maxvalue: 255||

### TemplateColorScheme

|Name|Type|Mandatory|Additional|Description|
|:---|:---|:--------|:---------|:----------|
|primaryColor|Common.RGBColor|false|||
|secondaryColor|Common.RGBColor|false|||
|backgroundColor|Common.RGBColor|false|||

### DisplayCapabilities

|Name|Type|Mandatory|Additional|Description|
|:---|:---|:--------|:---------|:----------|
|displayType|[Common.DisplayType](../enums/#displaytype)|true|||
|displayName|String|false||The name of the display the app is connected to.|
|textFields|Common.TextField|true|array: true<br>minsize: 0<br>maxsize: 100||
|imageFields|Common.ImageField|false|array: true<br>minsize: 1<br>maxsize: 100||
|mediaClockFormats|[Common.MediaClockFormat](../enums/#mediaclockformat)|true|array: true<br>minsize: 0<br>maxsize: 100||
|imageCapabilities|[Common.ImageType](../enums/#imagetype)|false|array: true<br>minsize: 0<br>maxsize: 2||
|graphicSupported|Boolean|true|||
|templatesAvailable|String|true|array: true<br>minsize: 0<br>maxsize: 100<br>maxlength: 100||
|screenParams|Common.ScreenParams|false|||
|numCustomPresetsAvailable|Integer|false|minvalue: 1<br>maxvalue: 100||

### TimeFormat

|Name|Type|Mandatory|Additional|Description|
|:---|:---|:--------|:---------|:----------|
|hours|Integer|true|minvalue: 0<br>maxvalue: 59||
|minutes|Integer|true|minvalue: 0<br>maxvalue: 59||
|seconds|Integer|true|minvalue: 0<br>maxvalue: 59||

### Image

|Name|Type|Mandatory|Additional|Description|
|:---|:---|:--------|:---------|:----------|
|value|String|true|maxlength: 65535|The path to the dynamic image stored on HU or the static binary image itself.<br>**Note:** There is no guarantee that the image reference is valid at the time it is received.|
|imageType|[Common.ImageType](../enums/#imagetype)|true||Describes whether it is a static or dynamic image.|
|isTemplate|Boolean|false||Optional value to specify whether it's a template image. A template image can be (re)colored by the HMI as needed by using an image pattern.|

### MyKey

|Name|Type|Mandatory|Additional|Description|
|:---|:---|:--------|:---------|:----------|
|e911Override|[Common.VehicleDataStatus](../enums/#vehicledatastatus)|true|||

### ImageField

|Name|Type|Mandatory|Additional|Description|
|:---|:---|:--------|:---------|:----------|
|name|[Common.ImageFieldName](../enums/#imagefieldname)|true|||
|imageTypeSupported|[Common.FileType](../enums/#filetype)|false|array: true<br>minsize: 1<br>maxsize: 100||
|imageResolution|Common.ImageResolution|false|||

### VideoStreamingFormat

|Name|Type|Mandatory|Additional|Description|
|:---|:---|:--------|:---------|:----------|
|protocol|[Common.VideoStreamingProtocol](../enums/#videostreamingprotocol)|true||Protocol type, see VideoStreamingProtocol|
|codec|[Common.VideoStreamingCodec](../enums/#videostreamingcodec)|true||Codec type, see VideoStreamingCodec|

### VideoConfig

|Name|Type|Mandatory|Additional|Description|
|:---|:---|:--------|:---------|:----------|
|protocol|[Common.VideoStreamingProtocol](../enums/#videostreamingprotocol)|false| |The video protocol configuration.|
|codec|[Common.VideoStreamingCodec](../enums/#videostreamingcodec)|false| |The video codec configuration.|
|width|Integer|false| |Width of the video stream, in pixels.|
|height|Integer|false| |Height of the video stream, in pixels.|

### ExternalConsentStatus

|Name|Type|Mandatory|Additional|Description|
|:---|:---|:--------|:---------|:----------|
|entityType|Integer|true|minvalue: 0<br>maxvalue: 128|The entityType which status is informed by "status" param.|
|entityID|Integer|true|minvalue: 0<br>maxvalue: 128|The corresponding ID of entityType which status is informed by "status" param.|
|status|[Common.EntityStatus](../enums/#entitystatus)|true||Status of External User Consent Settings entity: "ON" or "OFF"|

### ModuleData

|Name|Type|Mandatory|Additional|Description|
|:---|:---|:--------|:---------|:----------|
|moduleType|[Common.ModuleType](../enums/#moduletype)|true||The moduleType indicates which type of data should be changed and identifies which data object exists in this struct. For example, if the moduleType is CLIMATE then a "climateControlData" should exist|
|moduleId|String|false|maxlength: 100|Id of a module, published by System Capability.|
|radioControlData|Common.RadioControlData|false|||
|climateControlData|Common.ClimateControlData|false|||
|seatControlData|Common.SeatControlData|false|||
|audioControlData|Common.AudioControlData|false|||
|lightControlData|Common.LightControlData|false|||
|hmiSettingsControlData|Common.HMISettingsControlData|false|||

### RadioControlData

|Name|Type|Mandatory|Additional|Description|
|:---|:---|:--------|:---------|:----------|
|frequencyInteger|Integer|false|minvalue: 0<br>maxvalue: 1710|The integer part of the frequency ie for 101.7 this value should be 101|
|frequencyFraction|Integer|false|minvalue: 0<br>maxvalue: 9|The fractional part of the frequency for 101.7 is 7|
|band|[Common.RadioBand](../enums/#radioband)|false|||
|rdsData|Common.RdsData|false|||
|availableHDs|Integer|false|minvalue: 1<br>maxvalue: 7|Number of HD sub-channels if available. Deprecated.|
|hdChannel|Integer|false|minvalue: 0<br>maxvalue: 7|Current HD sub-channel if available.|
|signalStrength|Integer|false|minvalue: 0<br>maxvalue: 100||
|signalChangeThreshold|Integer|false|minvalue: 0<br>maxvalue: 100|If the signal strength falls below the set value for this parameter, the radio will tune to an alternative frequency|
|radioEnable|Boolean|false||True if the radio is on, false is the radio is off|
|state|[Common.RadioState](../enums/#radiostate)|false|||
|sisData|Common.SisData|false||Read-only Station Information Service (SIS) data provides basic information about the station such as call sign, as well as information not displayable to the consumer such as the station identification number|
|hdRadioEnable|Boolean|false||True if the hd radio is on, false is the radio is off|
|availableHdChannels|Integer|false|minvalue: 0<br>maxvalue: 7<br>array: true<br>minsize: 0<br>maxsize: 8|The list of available hd sub-channel indexes, empty list means no Hd channel is available, read-only|

### RdsData

|Name|Type|Mandatory|Additional|Description|
|:---|:---|:--------|:---------|:----------|
|PS|String|false|minlength: 0<br>maxlength: 8|Program Service Name|
|RT|String|false|minlength: 0<br>maxlength: 64|Radio Text|
|CT|String|false|minlength: 24<br>maxlength: 24|The clock text in <abbr title="Universal Time Coordinate">UTC</abbr> format as YYYY-MM-DDThh:mm:ss.sTZD|
|PI|String|false|minlength: 0<br>maxlength: 6|Program Identification - the call sign for the radio station|
|PTY|Integer|false|minvalue: 0<br>maxvalue: 31|The program type - The region should be used to differentiate between EU and North America program types|
|TP|Boolean|false||Traffic Program Identification - Identifies a station that offers traffic|
|TA|Boolean|false||Traffic Announcement Identification - Indicates an ongoing traffic announcement|
|REG|String|false||Region|

### StationIDNumber

|Name|Type|Mandatory|Additional|Description|
|:---|:---|:--------|:---------|:----------|
|countryCode|Integer|false|minvalue: 0<br>maxvalue: 999|Binary Representation of ITU Country Code. USA Code is 001.|
|fccFacilityId|Integer|false|minvalue: 0<br>maxvalue: 999999|Binary representation  of unique facility ID assigned by the FCC; FCC controlled for U.S. territory|

### SisData

|Name|Type|Mandatory|Additional|Description|
|:---|:---|:--------|:---------|:----------|
|stationShortName|String|false|minlength: 4<br>maxlength: 7|Identifies the 4-alpha-character station call sign plus an optional (-FM) extension|
|stationIDNumber|Common.StationIDNumber|false||Used for network Application. Consists of Country Code and FCC Facility ID.|
|stationLongName|String|false|minlength: 0<br>maxlength: 56|Identifies the station call sign or other identifying information in the long format.|
|stationLocation|Common.GPSData|false||Provides the 3-dimensional geographic station location.<br>HMI should include only `longitudeDegrees`, `latitudeDegrees`, `altitude` params providing SiSData|
|stationMessage|String|false|minlength: 0<br>maxlength: 56|May be used to convey textual information of general interest to the consumer such as weather forecasts or public service announcements. <br> Includes a high priority delivery feature to convey emergencies that may be in the listening area.|

### ClimateControlData

|Name|Type|Mandatory|Additional|Description|
|:---|:---|:--------|:---------|:----------|
|fanSpeed|Integer|false|minvalue: 0<br>maxvalue: 100||
|currentTemperature|Common.Temperature|false|||
|desiredTemperature|Common.Temperature|false|||
|acEnable|Boolean|false|||
|circulateAirEnable|Boolean|false|||
|autoModeEnable|Boolean|false|||
|defrostZone|[Common.DefrostZone](../enums/#defrostzone)|false|||
|dualModeEnable|Boolean|false|||
|acMaxEnable|Boolean|false|||
|ventilationMode|[Common.VentilationMode](../enums/#ventilationmode)|false|||
|heatedSteeringWheelEnable|Boolean|false||value false means disabled/turn off, value true means enabled/turn on.|
|heatedWindshieldEnable|Boolean|false||value false means disabled, value true means enabled.|
|heatedRearWindowEnable|Boolean|false||value false means disabled, value true means enabled.|
|heatedMirrorsEnable|Boolean|false||value false means disabled, value true means enabled.|  
|climateEnable|Boolean|false|||

### Temperature

|Name|Type|Mandatory|Additional|Description|
|:---|:---|:--------|:---------|:----------|
|unit|[Common.TemperatureUnit](../enums/#temperatureunit)|true||Temperature Unit|
|value|Float|true||The temperature value is in TemperatureUnit specified unit|

### RemoteControlCapabilities

|Name|Type|Mandatory|Additional|Description|
|:---|:---|:--------|:---------|:----------|
|climateControlCapabilities|Common.ClimateControlCapabilities|false|array: true<br>minsize: 1<br>maxsize: 100|If included, the platform supports RC climate controls. For this baseline version, maxsize=1. i.e. only one climate control module is supported|
|radioControlCapabilities|Common.RadioControlCapabilities|false|array: true<br>minsize: 1<br>maxsize: 100|If included, the platform supports RC radio controls. For this baseline version, maxsize=1. i.e. only one climate control module is supported|
|buttonCapabilities|Common.ButtonCapabilities|false|array: true<br>minsize: 1<br>maxsize: 100|If included, the platform supports RC button controls with the included button names|
|seatControlCapabilities|Common.SeatControlCapabilities|false|minsize: 1<br>maxsize: 100<br>array: true|If included, the platform supports seat controls.|
|audioControlCapabilities|Common.AudioControlCapabilities|false|minsize: 1<br>maxsize: 100<br>array: true| If included, the platform supports audio controls.|
|hmiSettingsControlCapabilities|Common.HMISettingsControlCapabilities|false||If included, the platform supports hmi setting controls.|
|lightControlCapabilities|Common.LightControlCapabilities|false||If included, the platform supports light controls.|

### ClimateControlCapabilities

|Name|Type|Mandatory|Additional|Description|
|:---|:---|:--------|:---------|:----------|
|moduleName|String|true|maxlength: 100|The short friendly name of the climate control module. It should not be used to identify a module by mobile application.|
|moduleInfo|Common.ModuleInfo|false||Information about a RC module, including its id.|
|fanSpeedAvailable|Boolean|false||Availability of the control of fan speed <br> True: Available, False: Not Available, Not present: Not Available.|
|currentTemperatureAvailable|Boolean|false||Availability of the reading of current temperature.<br>True: Available, False: Not Available, Not present: Not Available.|
|desiredTemperatureAvailable|Boolean|false||Availability of the control of desired temperature. <br> True: Available, False: Not Available, Not present: Not Available.|
|acEnableAvailable|Boolean|false||Availability of the control of turn on/off AC. <br> True: Available, False: Not Available, Not present: Not Available.|
|acMaxEnableAvailable|Boolean|false||Availability of the control of enable/disable air conditioning is ON on the maximum level. <br> True: Available, False: Not Available, Not present: Not Available.|
|circulateAirEnableAvailable|Boolean|false||Availability of the control of enable/disable circulate Air mode. <br> True: Available, False: Not Available, Not present: Not Available.|
|autoModeEnableAvailable|Boolean|false||Availability of the control of enable/disable auto mode. <br> True: Available, False: Not Available, Not present: Not Available.|
|dualModeEnableAvailable|Boolean|false||Availability of the control of enable/disable dual mode. <br> True: Available, False: Not Available, Not present: Not Available.|
|defrostZoneAvailable|Boolean|false||Availability of the control of defrost zones. <br> True: Available, False: Not Available, Not present: Not Available.|
|defrostZone|[Common.DefrostZone](../enums/#defrostzone)|false|array: true<br>minsize: 1<br>maxsize: 100|A set of all defrost zones that are controllable.|
|ventilationModeAvailable|Boolean|false|| Availability of the control of air ventilation mode. <br> True: Available, False: Not Available, Not present: Not Available.|
|ventilationMode|[Common.VentilationMode](../enums/#ventilationmode)|false|array: true<br>minsize: 1<br>maxsize: 100|A set of all ventilation modes that are controllable|
|heatedSteeringWheelAvailable|Boolean|false|| Availability of the control (enable/disable) of heated Steering Wheel. <br> True: Available, False: Not Available, Not present: Not Available.|
|heatedWindshieldAvailable|Boolean|false|| Availability of the control (enable/disable) of heated Windshield. <br> True: Available, False: Not Available, Not present: Not Available.|
|heatedRearWindowAvailable|Boolean|false|| Availability of the control (enable/disable) of heated Rear Window. <br> True: Available, False: Not Available, Not present: Not Available.|
|heatedMirrorsAvailable|Boolean|false|| Availability of the control (enable/disable) of heated Mirrors. <br> True: Available, False: Not Available, Not present: Not Available.|  
|climateEnableAvailable|Boolean|false|| Availability of the control of enable/disable climate control. <br> True: Available, False: Not Available, Not present: Not Available.|

### AudioControlCapabilities

|Name|Type|Mandatory|Additional|Description|
|:---|:---|:--------|:---------|:----------|
|moduleName|String|true|maxlength: 100|The short friendly name of the light control module. <br> It should not be used to identify a module by mobile application.|
|moduleInfo|Common.ModuleInfo|false||Information about a RC module, including its id.|
|sourceAvailable|Boolean|false||Availability of the control of audio source.|
|keepContextAvailable|Boolean|false||Availability of the parameter keepContext.|
|volumeAvailable|Boolean|false||Availability of the control of audio volume.|
|equalizerAvailable|Boolean|false||Availability of the control of Equalizer Settings.|
|equalizerMaxChannelId|Integer|false|minvalue: 1<br>maxvalue: 100|Must be included if equalizerAvailable=true, and assume all IDs starting from 1 to this value are valid.|

### EqualizerSettings

|Name|Type|Mandatory|Additional|Description|
|:---|:---|:--------|:---------|:----------|
|channelId|Integer|true|minvalue: 1<br>maxvalue: 100|Defines the equalizer channel id|
|channelName|String|false|maxlength: 50|Read-only channel / frequency name (e.i. "Treble, Midrange, Bass" or "125 Hz")|
|channelSetting|Integer|true|minvalue: 0<br>maxvalue: 100|Reflects the setting, from 0%-100%.|

### AudioControlData

|Name|Type|Mandatory|Additional|Description|
|:---|:---|:--------|:---------|:----------|
|source|[Common.PrimaryAudioSource](../enums/#primaryaudiosource)|false||In a getter response or a notification, it is the current primary audio source of the system. <br> In a setter request, it is the target audio source that the system shall switch to. <br> If the value is MOBILE_APP, the system shall switch to the mobile media app that issues the setter RPC.|
|keepContext|Boolean|false||This parameter shall not be present in any getter responses or notifications. <br> This parameter is optional in a setter request. The default value is false. <br> If it is false, the system not only changes the audio source but also brings the default infotainment system UI associated with the audio source to foreground and set the application to background. <br> If it is true, the system changes the audio source, but keeps the current application's context.|
|volume|Integer|false|minvalue: 0<br>maxvalue: 100|Reflects the volume of audio, from 0%-100%."|
|equalizerSettings|Common.EqualizerSettings|false|minsize: 1<br>maxsize: 100<br>array: true|Defines the list of supported channels (band) and their current/desired settings on HMI|

### LightCapabilities

|Name|Type|Mandatory|Additional|Description|
|:---|:---|:--------|:---------|:----------|
|name|[Common.LightName](../enums/#lightname)|true|||
|statusAvailable|Boolean|false||Indicates if the status (ON/OFF) can be set remotely. App shall not use read-only values (RAMP_UP/RAMP_DOWN/UNKNOWN/INVALID) in a setInteriorVehicleData request.|
|densityAvailable|Boolean|false||Indicates if the light's density can be set remotely (similar to a dimmer).|
|rgbColorSpaceAvailable|Boolean|false||Indicates if the light's color can be set remotely by using the sRGB color space.|

### LightControlCapabilities

|Name|Type|Mandatory|Additional|Description|
|:---|:---|:--------|:---------|:----------|
|moduleName|String|true|maxlength: 100|The short friendly name of the light control module. <br> It should not be used to identify a module by mobile application.|
|moduleInfo|Common.ModuleInfo|false||Information about a RC module, including its id.|
|supportedLights|Common.LightCapabilities|true|minsize: 1<br>maxsize: 100<br>array: true| An array of available LightCapabilities that are controllable.|

### LightState

|Name|Type|Mandatory|Additional|Description|
|:---|:---|:--------|:---------|:----------|
|id|[Common.LightName](../enums/#lightname)|true||The name of a light or a group of lights.|
|status|[Common.LightStatus](../enums/#lightstatus)|true|||
|density|Float|false|minvalue: 0<br>maxvalue: 1||
|color|Common.RGBColor|false|||

### LightControlData

|Name|Type|Mandatory|Additional|Description|
|:---|:---|:--------|:---------|:----------|
|lightState|Common.LightState|true|minsize: 1<br>maxsize: 100<br>array: true|An array of LightNames and their current or desired status. <br> Status of the LightNames that are not listed in the array shall remain unchanged.|

### HMISettingsControlCapabilities

|Name|Type|Mandatory|Additional|Description|
|:---|:---|:--------|:---------|:----------|
|moduleName|String|true|maxlength: 100|The short friendly name of the HMI setting module. <br> It should not be used to identify a module by mobile application.|
|moduleInfo|Common.ModuleInfo|false||Information about a RC module, including its id.|
|distanceUnitAvailable|Boolean|false||Availability of the control of distance unit.|
|temperatureUnitAvailable|Boolean|false||Availability of the control of temperature unit.|
|displayModeUnitAvailable|Boolean|false||Availability of the control of HMI display mode.|

### HMISettingsControlData

|Name|Type|Mandatory|Additional|Description|
|:---|:---|:--------|:---------|:----------|
|displayMode|[Common.DisplayMode](../enums/#displaymode)|false|||
|temperatureUnit|[Common.TemperatureUnit](../enums/#temperatureunit)|false|||
|distanceUnit|[Common.DistanceUnit](../enums/#distanceunit)|false|||

### RadioControlCapabilities

|Name|Type|Mandatory|Additional|Description|
|:---|:---|:--------|:---------|:----------|
|moduleName|String|true|maxlength: 100| The short friendly name of the climate control module. <br> It should not be used to identify a module by mobile application.|
|moduleInfo|Common.ModuleInfo|false||Information about a RC module, including its id.|
|radioEnableAvailable|Boolean|false||Availability of the control of enable/disable radio. <br> True: Available, False: Not Available, Not present: Not Available.|
|radioBandAvailable|Boolean|false||Availability of the control of radio band. <br> True: Available, False: Not Available, Not present: Not Available.|
|radioFrequencyAvailable|Boolean|false||Availability of the control of radio frequency. <br> True: Available, False: Not Available, Not present: Not Available.|
|hdChannelAvailable|Boolean|false||Availability of the control of HD radio channel. <br> True: Available, False: Not Available, Not present: Not Available|
|rdsDataAvailable|Boolean|false||Availability of the getting Radio Data System (RDS) data. <br> True: Available, False: Not Available, Not present: Not Available.|
|availableHDsAvailable|Boolean|false||Availability of the getting the number of available HD channels. <br> True: Available, False: Not Available, Not present: Not Available.|
|stateAvailable|Boolean|false|| Availability of the getting the Radio state. <br> True: Available, False: Not Available, Not present: Not Available.|
|signalStrengthAvailable|Boolean|false||Availability of the getting the signal strength. <br> True: Available, False: Not Available, Not present: Not Available.|
|signalChangeThresholdAvailable|Boolean|false||Availability of the getting the signal Change Threshold. <br> True: Available, False: Not Available, Not present: Not Available.|
|sisDataAvailable|Boolean|false|| Availability of the getting HD radio Station Information Service (SIS) data. <br> True: Available, False: Not Available, Not present: Not Available.|
|hdRadioEnableAvailable|Boolean|false|| Availability of the control of enable/disable HD radio. <br> True: Available, False: Not Available, Not present: Not Available.|
|siriusxmRadioAvailable|Boolean|false|| Availability of sirius XM radio. <br> True: Available, False: Not Available, Not present: Not Available.|
|availableHdChannelsAvailable|Boolean|false|| Availability of the list of available HD sub-channel indexes. <br> True: Available, False: Not Available, Not present: Not Available.|

### ExternalConsentStatus

|Name|Type|Mandatory|Additional|Description|
|:---|:---|:--------|:---------|:----------|
|entityType|Integer|true|minvalue: 0<br>maxvalue: 128|The entityType which status is informed by "status" param.|
|entityID|Integer|true|minvalue: 0<br>maxvalue: 128|The corresponding ID of entityType which status is informed by "status" param.|
|status|[Common.EntityStatus](../enums/#entitystatus)|true||Status of External User Consent Settings entity: "ON" or "OFF"|

### Rectangle

|Name|Type|Mandatory|Additional|Description|
|:---|:---|:--------|:---------|:----------|
|x|Float|true| |The X-coordinate of the rectangle|
|y|Float|true| |The Y-coordinate of the rectangle|
|width|Float|true| |The width of the rectangle|
|height|Float|true| |The height of the rectangle|

### HapticRect

|Name|Type|Mandatory|Additional|Description|
|:---|:---|:--------|:---------|:----------|
|id|Integer|true|minvalue: 0<br>maxvalue: 2000000000|A unique identifier for the haptic rectangle|
|rect|Common.Rectangle|true| |The position of the haptic rectangle to be highlighted.<br>The center of this rectangle is considered "touched" when the element is focused and then selected.|

### FuelRange

|Name|Type|Mandatory|Additional|Description|
|:---|:---|:--------|:---------|:----------|
|type|[Common.FuelType](../enums/#fueltype)|false|||
|range|Float|false|minvalue: 0<br>maxvalue: 10000|The estimate range in KM the vehicle can travel based on fuel level and consumption|
|level|Float|false|minvalue: -6<br>maxvalue: 1000000|The relative remaining capacity of this fuel type (percentage)|
|levelState|[Common.ComponentVolumeStatus](../enums/#componentvolumestatus)|false||The fuel level state|
|capacity|Float|false|minvalue: 0<br>maxvalue: 1000000|The absolute capacity of this fuel type|
|capacityUnit|[Common.CapacityUnit](../enums/#capacityunit)|false||The unit of the capacity of this fuel type such as liters for gasoline or kWh for batteries|

### MassageModeData

|Name|Type|Mandatory|Additional|Description|
|:---|:---|:--------|:---------|:----------|
|massageZone|[Common.MassageZone](../enums/#massagezone)|true|||
|massageMode|[Common.MassageMode](../enums/#massagemode)|true|||

### MassageCushionFirmness

|Name|Type|Mandatory|Additional|Description|
|:---|:---|:--------|:---------|:----------|
|cushion|[Common.MassageCushion](../enums/#massagecushion)|true|||
|firmness|Integer|true|minvalue: 0<br>maxvalue: 100||

### SeatMemoryAction

|Name|Type|Mandatory|Additional|Description|
|:---|:---|:--------|:---------|:----------|
|id|Integer|true|minvalue: 1<br>maxvalue: 10||
|label|String|false|maxlength: 100||
|action|[Common.SeatMemoryActionType](../enums/#seatmemoryactiontype)|true|||

### SeatControlData

|Name|Type|Mandatory|Additional|Description|
|:---|:---|:--------|:---------|:----------|
|id|[Common.SupportedSeat](../enums/#supportedseat)|false|||
|heatingEnabled|Boolean|false|||
|coolingEnabled|Boolean|false|||
|heatingLevel|Integer|false|minvalue: 0<br>maxvalue: 100||
|coolingLevel|Integer|false|minvalue: 0<br>maxvalue: 100||
|horizontalPosition|Integer|false|minvalue: 0<br>maxvalue: 100||
|verticalPosition|Integer|false|minvalue: 0<br>maxvalue: 100||
|frontVerticalPosition|Integer|false|minvalue: 0<br>maxvalue: 100||
|backVerticalPosition|Integer|false|minvalue: 0<br>maxvalue: 100||
|backTiltAngle|Integer|false|minvalue: 0<br>maxvalue: 100||
|headSupportHorizontalPosition|Integer|false|minvalue: 0<br>maxvalue: 100||
|headSupportVerticalPosition|Integer|false|minvalue: 0<br>maxvalue: 100||
|massageEnabled|Boolean|false|||
|massageMode|Common.MassageModeData|false|minsize: 1<br>maxsize: 2<br>array: true||
|massageCushionFirmness|Common.MassageCushionFirmness|false|minsize: 1<br>maxsize: 5<br>array: true||
|memory|Common.SeatMemoryAction|false|||

### SeatControlCapabilities

|Name|Type|Mandatory|Additional|Description|
|:---|:---|:--------|:---------|:----------|
|moduleName|String|true|maxlength: 100|The short friendly name of the light control module. <br> It should not be used to identify a module by mobile application.|
|moduleInfo|Common.ModuleInfo|false||Information about a RC module, including its id.|
|heatingEnabledAvailable|Boolean|false|||
|coolingEnabledAvailable|Boolean|false|||
|heatingLevelAvailable|Boolean|false|||
|coolingLevelAvailable|Boolean|false|||
|horizontalPositionAvailable|Boolean|false|||
|verticalPositionAvailable|Boolean|false|||
|frontVerticalPositionAvailable|Boolean|false|||
|backVerticalPositionAvailable|Boolean|false|||
|backTiltAngleAvailable|Boolean|false|||
|headSupportHorizontalPositionAvailable|Boolean|false|||
|headSupportVerticalPositionAvailable|Boolean|false|||
|massageEnabledAvailable|Boolean|false|||
|massageModeAvailable|Boolean|false|||
|massageCushionFirmnessAvailable|Boolean|false|||
|memoryAvailable|Boolean|false|||

### DateTime

|Name|Type|Mandatory|Additional|Description|
|:---|:---|:--------|:---------|:----------|
|millisecond|Integer|false|minvalue: 0<br>maxvalue: 999|Milliseconds – part of time - one thousandth split second|
|second|Integer|false|minvalue: 0<br>maxvalue: 60|Seconds part of time|
|minute|Integer|false|minvalue: 0<br>maxvalue: 59|Minutes part of time|
|hour|Integer|false|minvalue: 0<br>maxvalue: 23|Hours part of time. Note that this structure accepts time only in 24 Hr format|
|day|Integer|false|minvalue: 1<br>maxvalue: 31|Day of the month|
|month|Integer|false|minvalue: 1<br>maxvalue: 12|Month of the year|
|year|Integer|false|maxvalue: 4095|The year in YYYY format|
|tz_hour|Integer|false|minvalue: -12<br>maxvalue: 14<br>defvalue: 0|Time zone offset in Hours with regard to <abbr title="Universal Time Coordinate">UTC</abbr>.|
|tz_minute|Integer|false|minvalue: 0<br>maxvalue: 59<br>defvalue: 0|Time zone offset in Min with regard to <abbr title="Universal Time Coordinate">UTC</abbr>.|

### Coordinate

|Name|Type|Mandatory|Additional|Description|
|:---|:---|:--------|:---------|:----------|
|latitudeDegrees|Float|true|minvalue: -90<br>maxvalue: 90|Latitude of the location|
|longitudeDegrees|Float|true|minvalue: -180<br>maxvalue: 180|Longitude of the location|

### OASISAddress

|Name|Type|Mandatory|Additional|Description|
|:---|:---|:--------|:---------|:----------|
|countryName|String|false|minlength: 0<br>maxlength: 200|Name of the country (localized)|
|countryCode|String|false|minlength: 0<br>maxlength: 50|Name of country (ISO 3166-2)|
|postalCode|String|false|minlength: 0<br>maxlength: 16|(PLZ, ZIP, PIN, CAP etc.)|
|administrativeArea|String|false|minlength: 0<br>maxlength: 200|Portion of country (e.g. state)|
|subAdministrativeArea|String|false|minlength: 0<br>maxlength: 200|Portion of administrativeArea (e.g. county)|
|locality|String|false|minlength: 0<br>maxlength: 200|Hypernym for city/village|
|subLocality|String|false|minlength: 0<br>maxlength: 200|Hypernym for district|
|thoroughfare|String|false|minlength: 0<br>maxlength: 200|Hypernym for street, road etc|
|subThoroughfare|String|false|minlength: 0<br>maxlength: 200|Portion of thoroughfare (e.g. house number)|

### LocationDetails

|Name|Type|Mandatory|Additional|Description|
|:---|:---|:--------|:---------|:----------|
|coordinate|Common.Coordinate|false||Latitude/Longitude of the location|
|locationName|String|false|maxlength: 500|Name of location|
|addressLines|String|false|maxlength: 500<br>array: true<br>minsize: 0<br>maxsize: 4|Location address for display purposes only|
|locationDescription|String|false|maxlength: 500|Description intended location/establishment (if applicable)|
|phoneNumber|String|false|maxlength: 500|Phone number of location/establishment|
|locationImage|Common.Image|false||Image/icon of intended location|
|searchAddress|Common.OASISAddress|false||Address to be used by navigation engines for search|

### SyncMsgVersion

|Name|Type|Mandatory|Additional|Description|
|:---|:---|:--------|:---------|:----------|
|majorVersion|Integer|true|minvalue: 1<br>maxvalue: 10|The major version indicates versions that is not-compatible to previous versions|
|minorVersion|Integer|true|minvalue: 0<br>maxvalue: 1000|The minor version indicates a change to a previous version that should still allow to be run on an older version (with limited functionality)|
|patchVersion|Integer|false|minvalue: 0<br>maxvalue: 1000|The patch version indicates a fix to existing functionality in a previous version that should still be able to be run on an older version|

### AppServiceManifest

|Name|Type|Mandatory|Additional|Description|
|:---|:---|:--------|:---------|:----------|
|serviceName|String|false||Unique name of this service|
|serviceType|String|true||The type of service that is to be offered by this app|
|serviceIcon|Common.Image|false||The icon to be associated with this service. Most likely the same as the appIcon|
|allowAppConsumers|Boolean|false|defvalue: false|If true, app service consumers beyond the <abbr title="In Vehicle Infotainment">IVI</abbr> system will be able to access this service. If false, only the <abbr title="In Vehicle Infotainment">IVI</abbr> system will be able consume the service. If not provided, it is assumed to be false|
|rpcSpecVersion|Common.SyncMsgVersion|false||This is the max RPC Spec version the app service understands. This is important during the RPC passthrough functionality. If not included, it is assumed the max version of the module is acceptable|
|handledRPCs|Integer|false|array: true|This field contains the Function IDs for the RPCs that this service intends to handle correctly. This means the service will provide meaningful responses|
|mediaServiceManifest|Common.MediaServiceManifest|false|||
|weatherServiceManifest|Common.WeatherServiceManifest|false|||
|navigationServiceManifest|Common.NavigationServiceManifest|false|||

### AppServiceRecord

|Name|Type|Mandatory|Additional|Description|
|:---|:---|:--------|:---------|:----------|
|serviceID|String|true||A unique ID tied to this specific service record. The ID is supplied by the module that services publish themselves|
|serviceManifest|Common.AppServiceManifest|true||Manifest for the service that this record is for|
|servicePublished|Boolean|true||If true, the service is published and available. If false, the service has likely just been unpublished, and should be considered unavailable|
|serviceActive|Boolean|true||If true, the service is the active primary service of the supplied service type. It will receive all potential RPCs that are passed through to that service type. If false, it is not the primary service of the supplied type. See servicePublished for its availability|

### AppServiceData

|Name|Type|Mandatory|Additional|Description|
|:---|:---|:--------|:---------|:----------|
|serviceType|String|true||The type of service that is to be offered by this app. See AppServiceType for known enum equivalent types. Parameter is a string to allow for new service types to be used by apps on older versions of SDL Core|
|serviceID|String|true||A unique ID tied to this specific service|
|mediaServiceData|Common.MediaServiceData|false|||
|weatherServiceData|Common.WeatherServiceData|false|||
|navigationServiceData|Common.NavigationServiceData|false|||

### AppServiceCapability

|Name|Type|Mandatory|Additional|Description|
|:---|:---|:--------|:---------|:----------|
|updateReason|[Common.ServiceUpdateReason](../enums/#serviceupdatereason)|false||Only included in OnSystemCapabilityUpdated. Update reason for service record|
|updatedAppServiceRecord|Common.AppServiceRecord|true||Service record for a specific app service provider|

### AppServicesCapabilities

|Name|Type|Mandatory|Additional|Description|
|:---|:---|:--------|:---------|:----------|
|appServices|Common.AppServiceCapability|false|array: true|An array of currently available services. If this is an update to the capability the affected services will include an update reason in that item|

### SystemCapability

|Name|Type|Mandatory|Additional|Description|
|:---|:---|:--------|:---------|:----------|
|systemCapabilityType|[Common.SystemCapabilityType](../enums/#systemcapabilitytype)|true||Used as a descriptor of what data to expect in this struct. The corresponding param to this enum should be included and the only other param included|
|navigationCapability|Common.NavigationCapability|false||Describes extended capabilities for onboard navigation system|
|phoneCapability|Common.PhoneCapability|false||Describes extended capabilities of the module's phone feature|
|videoStreamingCapability|Common.VideoStreamingCapability|false||Describes extended capabilities of the module's phone feature|
|remoteControlCapability|Common.RemoteControlCapabilities|false||Describes extended capabilities of the module's phone feature|
|appServicesCapabilities|Common.AppServicesCapabilities|false||An array of currently available services. If this is an update to the capability the affected services will include an update reason in that item|
|displayCapabilities|Common.DisplayCapability|false|array: true<br>minsize: 1<br>maxsize: 1000||
|seatLocationCapability|Common.SeatLocationCapability|false||Contains information about the locations of each seat|
|driverDistractionCapability|Common.DriverDistractionCapability|false||Describes capabilities when the driver is distracted|

### MediaServiceManifest

There are no defined parameters for this struct

### MediaServiceData

|Name|Type|Mandatory|Additional|Description|
|:---|:---|:--------|:---------|:----------|
|mediaType|[Common.MediaType](../enums/#mediatype)|false||The type of the currently playing or paused track|
|mediaTitle|String|false||Music: The name of the current track<br>Podcast: The name of the current episode<br>Audiobook: The name of the current chapter|
|mediaArtist|String|false||Music: The name of the current album artist<br>Podcast: The provider of the podcast (hosts, network, company)<br>Audiobook: The book author's name|
|mediaAlbum|String|false||Music: The name of the current album<br>Podcast: The name of the current podcast show<br>Audiobook: The name of the current book|
|playlistName|String|false||Music: The name of the playlist or radio station, if the user is playing from a playlist, otherwise, Null<br>Podcast: The name of the playlist, if the user is playing from a playlist, otherwise, Null<br>Audiobook: Likely not applicable, possibly a collection or "playlist" of books|
|isExplicit|Boolean|false||Whether or not the content currently playing (e.g. the track, episode, or book) contains explicit content|
|trackPlaybackProgress|Integer|false||Music: The current progress of the track in seconds<br>Podcast: The current progress of the episode in seconds<br>Audiobook: The current progress of the current segment (e.g. the chapter) in seconds|
|trackPlaybackDuration|Integer|false||Music: The total duration of the track in seconds<br>Podcast: The total duration of the episode in seconds<br>Audiobook: The total duration of the current segment (e.g. the chapter) in seconds|
|queuePlaybackProgress|Integer|false||Music: The current progress of the playback queue in seconds<br>Podcast: The current progress of the playback queue in seconds<br>Audiobook: The current progress of the playback queue (e.g. the book) in seconds|
|queuePlaybackDuration|Integer|false||Music: The total duration of the playback queue in seconds<br>Podcast: The total duration of the playback queue in seconds<br>Audiobook: The total duration of the playback queue (e.g. the book) in seconds|
|queueCurrentTrackNumber|Integer|false||Music: The current number (1 based) of the track in the playback queue<br>Podcast: The current number (1 based) of the episode in the playback queue<br>Audiobook: The current number (1 based) of the episode in the playback queue (e.g. the chapter number in the book)|
|queueTotalTrackCount|Integer|false||Music: The total number of tracks in the playback queue<br>Podcast: The total number of episodes in the playback queue<br>Audiobook: The total number of sections in the playback queue (e.g. the number of chapters in the book)|
|mediaImage|Common.Image|false||Music: The album art of the current track<br>Podcast: The podcast or chapter artwork of the current podcast episode<br>Audiobook: The book or chapter artwork of the current audiobook|

### WeatherServiceManifest

|Name|Type|Mandatory|Additional|Description|
|:---|:---|:--------|:---------|:----------|
|currentForecastSupported|Boolean|false|||
|maxMultidayForecastAmount|Integer|false|||
|maxHourlyForecastAmount|Integer|false|||
|maxMinutelyForecastAmount|Integer|false|||
|weatherForLocationSupported|Boolean|false|||

### WeatherAlert

|Name|Type|Mandatory|Additional|Description|
|:---|:---|:--------|:---------|:----------|
|title|String|false|||
|summary|String|false|||
|expires|Common.DateTime|false|||
|regions|String|false|array: true<br>minsize: 1<br>maxsize: 99||
|severity|String|false|||
|timeIssued|Common.DateTime|false|||

### WeatherData

|Name|Type|Mandatory|Additional|Description|
|:---|:---|:--------|:---------|:----------|
|currentTemperature|Common.Temperature|false|||
|temperatureHigh|Common.Temperature|false|||
|temperatureLow|Common.Temperature|false|||
|apparentTemperature|Common.Temperature|false|||
|apparentTemperatureHigh|Common.Temperature|false|||
|apparentTemperatureLow|Common.Temperature|false|||
|weatherSummary|String|false|||
|time|Common.DateTime|false|||
|humidity|Float|false|minvalue: 0<br>maxvalue: 1|0 to 1, percentage humidity|
|cloudCover|Float|false|minvalue: 0<br>maxvalue: 1|0 to 1, percentage cloud cover|
|moonPhase|Float|false|minvalue: 0<br>maxvalue: 1|0 to 1, percentage of the moon seen, e.g. 0 = no moon, 0.25 = quarter moon|
|windBearing|Integer|false||In degrees, true north at 0 degrees|
|windGust|Float|false||km/hr|
|windSpeed|Float|false||km/hr|
|nearestStormBearing|Integer|false||In degrees, true north at 0 degrees|
|nearestStormDistance|Integer|false||In km|
|precipAccumulation|Float|false||cm|
|precipIntensity|Float|false||cm of water per hour|
|precipProbability|Float|false|minvalue: 0<br>maxvalue: 1|0 to 1, percentage chance|
|precipType|String|false||e.g. "rain", "snow", "sleet", "hail"|
|visibility|Float|false||In km|
|weatherIcon|Common.Image|false|||

### WeatherServiceData

|Name|Type|Mandatory|Additional|Description|
|:---|:---|:--------|:---------|:----------|
|location|Common.LocationDetails|true|||
|currentForecast|Common.WeatherData|false|||
|minuteForecast|Common.WeatherData|false|array: true<br>minsize: 15<br>maxsize: 60||
|hourlyForecast|Common.WeatherData|false|array: true<br>minsize: 1<br>maxsize: 96||
|multidayForecast|Common.WeatherData|false|array: true<br>minsize: 1<br>maxsize: 30||
|alerts|Common.WeatherAlert|false|array: true<br>minsize: 1<br>maxsize: 10|This array should be ordered with the first object being the current day|

### NavigationServiceManifest

|Name|Type|Mandatory|Additional|Description|
|:---|:---|:--------|:---------|:----------|
|acceptsWayPoints|Boolean|false||Informs the subscriber if this service can actually accept way points|

### NavigationInstruction

|Name|Type|Mandatory|Additional|Description|
|:---|:---|:--------|:---------|:----------|
|locationDetails|Common.LocationDetails|true|||
|action|[Common.NavigationAction](../enums/#navigationaction)|true|||
|eta|Common.DateTime|false|||
|bearing|Integer|false|minvalue: 0<br>maxvalue: 359|The angle at which this instruction takes place. For example, 0 would mean straight, less than 45 is bearing right, greater than 135 is sharp right, between 45 and 135 is a regular right, and 180 is a U-Turn, etc|
|junctionType|[Common.NavigationJunction](../enums/#navigationjunction)|false|||
|drivingSide|[Common.Direction](../enums/#direction)|false||Used to infer which side of the road this instruction takes place. For a U-Turn (action=TURN, bearing=180) this will determine which direction the turn should take place|
|details|String|false||This is a string representation of this instruction, used to display instructions to the users. This is not intended to be read aloud to the users, see the param prompt in NavigationServiceData for that|
|image|Common.Image|false||An image representation of this instruction|

### NavigationServiceData

|Name|Type|Mandatory|Additional|Description|
|:---|:---|:--------|:---------|:----------|
|timeStamp|Common.DateTime|true||This is the timestamp of when the data was generated. This is to ensure any time or distance given in the data can accurately be adjusted if necessary|
|origin|Common.LocationDetails|false|||
|destination|Common.LocationDetails|false|||
|destinationETA|Common.DateTime|false|||
|instructions|Common.NavigationInstruction|false|array: true|This array should be ordered with all remaining instructions. The start of this array should always contain the next instruction|
|nextInstructionETA|Common.DateTime|false|||
|nextInstructionDistance|Float|false||The distance to this instruction from current location. This should only be updated ever .1 unit of distance. For more accuracy the consumer can use the <abbr title="Global Positioning System">GPS</abbr> location of itself and the next instruction|
|nextInstructionDistanceScale|Float|false||Distance till next maneuver (starting from) from previous maneuver|
|prompt|String|false||This is a prompt message that should be conveyed to the user through either display or voice (<abbr title="Text To Speech">TTS</abbr>). This param will change often as it should represent the following: approaching instruction, post instruction, alerts that affect the current navigation session, etc|

### TemplateConfiguration

|Name|Type|Mandatory|Additional|Description|
|:---|:---|:--------|:---------|:----------|
|template|String|true|maxlength: 500| Predefined or dynamically created window template. Currently only predefined window template layouts are defined.|
|dayColorScheme|Common.TemplateColorScheme|false|||
|nightColorScheme|Common.TemplateColorScheme|false|||

### DisplayCapability

|Name|Type|Mandatory|Additional|Description|
|:---|:---|:--------|:---------|:----------|
|displayName|String|false|||
|windowTypeSupported|Common.WindowTypeCapabilities|false|array: true<br>minsize: 1|Informs the application how many windows the app is allowed to create per type|
|windowCapabilities|Common.WindowCapability|false|array: true<br>minsize: 1<br>maxsize: 1000|Contains a list of capabilities of all windows related to the app.<br>Once the app has registered the capabilities of all windows are provided.<br>GetSystemCapability still allows requesting window capabilities of all windows.|

### WindowTypeCapabilities

|Name|Type|Mandatory|Additional|Description|
|:---|:---|:--------|:---------|:----------|
|type|[Common.WindowType](../enums/#windowtype)|true|||
|maximumNumberOfWindows|Integer|true|||

### WindowCapability

|Name|Type|Mandatory|Additional|Description|
|:---|:---|:--------|:---------|:----------|
|windowID|Integer|false||The specified ID of the window. Can be set to a predefined window, or omitted for the main window on the main display.|
|textFields|Common.TextField|false|array: true<br>minsize: 1<br>maxsize: 100|A set of all fields that support text data. See TextField|
|imageFields|Common.ImageField|false|array: true<br>minsize: 1<br>maxsize: 100|A set of all fields that support images. See ImageField|
|imageTypeSupported|[Common.ImageType](../enums/#imagetype)|false|array: true<br>minsize: 0<br>maxsize: 1000|Provides information about image types supported by the system.|
|templatesAvailable|String|false|array: true<br>minsize: 0<br>maxsize: 100<br>maxlength: 100|A set of all window templates available on the head unit.|
|numCustomPresetsAvailable|Integer|false|minvalue: 1<br>maxvalue: 100|The number of on-window custom presets available (if any); otherwise omitted.|
|buttonCapabilities|Common.ButtonCapabilities|false|array: true<br>minsize: 1<br>maxsize: 100|The number of buttons and the capabilities of each on-window button.|
|softButtonCapabilities|Common.SoftButtonCapabilities|false|array: true<br>minsize: 1<br>maxsize: 100|The number of soft buttons available on-window and the capabilities for each button.|
|menuLayoutsAvailable|[Common.MenuLayout](../enums/#menulayout)|false|array: true<br>minsize: 1<br>maxsize: 1000|An array of available menu layouts. If this parameter is not provided, only the `LIST` layout is assumed to be available|

### ModuleInfo

|Name|Type|Mandatory|Additional|Description|
|:---|:---|:--------|:---------|:----------|
|moduleId|String|true|maxlength: 100|uuid of a module. "moduleId + moduleType" uniquely identify a module.| 
|location|Common.Grid|false||Location of a module.|
|serviceArea|Common.Grid|false||Service area of a module.|
|allowMultipleAccess|Boolean|false|defvalue: true|allow multiple users/apps to access the module or not|

### Grid

|Name|Type|Mandatory|Additional|Description|
|:---|:---|:--------|:---------|:----------|
|col|Integer|true|minvalue: -1<br>maxvalue: 100|Describes a location (origin coordinates and span) of a vehicle component.|
|row|Integer|true|minvalue: -1<br>maxvalue: 100|Describes a location (origin coordinates and span) of a vehicle component.|
|level|Integer|false|minvalue: -1<br>maxvalue: 100<br>defvalue: 0|Describes a location (origin coordinates and span) of a vehicle component.|
|colspan|Integer|false|minvalue: 1<br>maxvalue: 100<br>defvalue: 1|Describes a location (origin coordinates and span) of a vehicle component.|
|rowspan|Integer|false|minvalue: 1<br>maxvalue: 100<br>defvalue: 1|Describes a location (origin coordinates and span) of a vehicle component.|
|levelspan|Integer|false|minvalue: 1<br>maxvalue: 100<br>defvalue: 1|Describes a location (origin coordinates and span) of a vehicle component.|

### SeatLocationCapability

|Name|Type|Mandatory|Additional|Description|
|:---|:---|:--------|:---------|:----------|
|rows|Integer|false|minvalue: 1<br>maxvalue: 100|Contains information about the locations of each seat.|
|columns|Integer|false|minvalue: 1<br>maxvalue: 100|Contains information about the locations of each seat.|
|levels|Integer|false|minvalue: 1<br>maxvalue: 100<br>defvalue: 1|Contains information about the locations of each seat.|
|seats|Common.SeatLocation|false|array: true|Contains a list of SeatLocation in the vehicle, the first element is the driver's seat|

### SeatLocation

|Name|Type|Mandatory|Additional|Description|
|:---|:---|:--------|:---------|:----------|
|grid|Common.Grid|false||Describes the location of a seat. HMI shall include this parameter when publishing seat locations in capabilities.|

### AppProperties

|Name|Type|Mandatory|Additional|Description|
|:---|:---|:--------|:---------|:----------|
|nicknames|String|false|minlength: 0<br>maxlength: 100<br>array: true<br>minsize: 0<br>maxsize: 100|An array of app names an app is allowed to register with. If included in a SetAppProperties request, this value will overwrite the existing "nicknames" field in the app policies section of the policy table|
|policyAppID|String|true|minlength: 1<br>maxlength: 100||
|enabled|Boolean|false||If true, the app will be marked as "available" or "installed" and will be included in HMI RPC UpdateAppList|
|authToken|String|false|maxlength: 65535|Used to authenticate connection on app activation|
|transportType|String|false|maxlength: 100|Specifies the connection type Core should use. The Core role (server or client) is dependent of "endpoint" being specified.<br>See "endpoint" for details|
|hybridAppPreference|[Common.HybridAppPreference](../enums/#hybridapppreference)|false||Specifies the user preference to use one specific app type or all available types|
|endpoint|String|false|maxlength: 65535|If specified, which Core uses a client implementation of the connection type and attempts to connect to the endpoint when this app is selected (activated).<br>If omitted, Core won't attempt to connect as the app selection (activation) is managed outside of Core. Instead it uses a server implementation of the connection type and expects the app to connect|

### GearStatus

|Name|Type|Mandatory|Additional|Description|
|:---|:---|:--------|:---------|:----------|
|userSelectedGear|[Common.PRNDL](../enums/#prndl)|false||Gear position selected by the user<br>i.e. Park, Drive, Reverse|
|actualGear|[Common.PRNDL](../enums/#prndl)|false||Actual Gear in use by the transmission|
|transmissionType|[Common.TransmissionType](../enums/#transmissiontype)|false||Tells the transmission type|

### StabilityControlsStatus

|Name|Type|Mandatory|Additional|Description|
|:---|:---|:--------|:---------|:----------|
|escSystem|[Common.VehicleDataStatus](../enums/#vehicledatastatus)|false||true if vehicle stability control is ON,<br>else false|
|trailerSwayControl|[Common.VehicleDataStatus](../enums/#vehicledatastatus)|false||true if vehicle trailer sway control is ON,<br>else false|

### WindowState

|Name|Type|Mandatory|Additional|Description|
|:---|:---|:--------|:---------|:----------|
|approximatePosition|Integer|true|minvalue: 0<br>maxvalue: 100|The approximate percentage that the window is open -<br>0 being fully closed, 100 being fully open|
|deviation|Integer|true|minvalue: 0<br>maxvalue: 100|The percentage deviation of the approximatePosition.<br>e.g. If the approximatePosition is 50 and the deviation is 10,<br>then the window's location is somewhere between 40 and 60|

### WindowStatus

|Name|Type|Mandatory|Additional|Description|
|:---|:---|:--------|:---------|:----------|
|location|Common.Grid|true|||
|state|Common.WindowState|true|||
