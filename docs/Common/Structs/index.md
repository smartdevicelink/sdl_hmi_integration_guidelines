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
|navigation|Boolean|false|||
|phoneCall|Boolean|false|||

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
|maxBitrate|Integer|false|minvalue: 0<br>maxvalue: 2147483647|The maximum bitrate of video stream that is supported, in kbps.|
|supportedFormats|Common.VideoStreamingFormat|false|array: true|Detailed information on each format supported by this system, in its preferred order.|
|hapticSpatialDataSupported|boolean|false| |True if the system can utilize the haptic spatial data from the source being streamed.|


### SystemCapabilities

|Name|Type|Mandatory|Additional|Description|
|:---|:---|:--------|:---------|:----------|
|navigationCapability|Common.NavigationCapability|false|||
|phoneCapability|Common.PhoneCapability|false|||
|videoStreamingCapability|Common.VideoStreamingCapability|false|||

### MenuParams

|Name|Type|Mandatory|Additional|Description|
|:---|:---|:--------|:---------|:----------|
|parentID|Integer|false|minvalue: 0<br>maxvalue: 2000000000||
|position|Integer|false|minvalue: 0<br>maxvalue: 1000||
|menuName|String|true|maxlength: 500||

### TireStatus

|Name|Type|Mandatory|Additional|Description|
|:---|:---|:--------|:---------|:----------|
|pressureTelltale|Common.WarningLightStatus|false|||
|leftFront|Common.SingleTireStatus|false|||
|rightFront|Common.SingleTireStatus|false|||
|leftRear|Common.SingleTireStatus|false|||
|rightRear|Common.SingleTireStatus|false|||
|innerLeftRear|Common.SingleTireStatus|false|||
|innerRightRear|Common.SingleTireStatus|false|||

### ECallInfo

|Name|Type|Mandatory|Additional|Description|
|:---|:---|:--------|:---------|:----------|
|eCallNotificationStatus|Common.VehicleDataNotificationStatus||||
|auxECallNotificationStatus|Common.VehicleDataNotificationStatus||||
|eCallConfirmationStatus|Common.ECallConfirmationStatus||||

### DIDResult

|Name|Type|Mandatory|Additional|Description|
|:---|:---|:--------|:---------|:----------|
|resultCode|Common.VehicleDataResultCode|true|||
|didLocation|Integer|true|minvalue: 0<br>maxvalue: 65535||
|data|String|false|maxlength: 5000||

### TTSChunk

|Name|Type|Mandatory|Additional|Description|
|:---|:---|:--------|:---------|:----------|
|text|String|true|maxlength: 500|The text/phonemes to be spoken or the name of an audio file to play|
|type|Common.SpeechCapabilities|true||Describes how to interpret the text field (as plain text, a file name, etc.)|

### TextField

|Name|Type|Mandatory|Additional|Description|
|:---|:---|:--------|:---------|:----------|
|name|Common.TextFieldName||||
|characterSet|Common.CharacterSet||||
|width|Integer||minvalue: 1<br>maxvalue: 500||
|rows|Integer||minvalue: 1<br>maxvalue: 8||

### TouchCoord

|Name|Type|Mandatory|Additional|Description|
|:---|:---|:--------|:---------|:----------|
|x|Integer|true|minvalue: 0<br>maxvalue: 10000||
|y|Integer|true|minvalue: 0<br>maxvalue: 10000||

### AudioPassThruCapabilities

|Name|Type|Mandatory|Additional|Description|
|:---|:---|:--------|:---------|:----------|
|samplingRate|Common.SamplingRate|true|||
|bitsPerSample|Common.BitsPerSample|true|||
|audioType|Common.AudioType|true|||

### ServiceInfo

|Name|Type|Mandatory|Additional|Description|
|:---|:---|:--------|:---------|:----------|
|url|String|true|||
|policyAppId|String|false|||

### HeadLampStatus

|Name|Type|Mandatory|Additional|Description|
|:---|:---|:--------|:---------|:----------|
|lowBeamsOn|Boolean|true|||
|highBeamsOn|Boolean|true|||
|ambientLightSensorStatus|Common.AmbientLightStatus|true|||

### ClusterModeStatus

|Name|Type|Mandatory|Additional|Description|
|:---|:---|:--------|:---------|:----------|
|powerModeActive|Boolean||||
|powerModeQualificationStatus|Common.PowerModeQualificationStatus||||
|carModeStatus|Common.CarModeStatus||||
|powerModeStatus|Common.PowerModeStatus||||

### KeyboardProperties

|Name|Type|Mandatory|Additional|Description|
|:---|:---|:--------|:---------|:----------|
|language|Common.Language|false|||
|keyboardLayout|Common.KeyboardLayout|false|||
|keypressMode|Common.KeypressMode|false|||
|limitedCharacterList|String|false|array: true<br>minsize: 1<br>maxsize: 100<br>maxlength: 1||
|autoCompleteText|String|false|maxlength: 1000||

### Choice

|Name|Type|Mandatory|Additional|Description|
|:---|:---|:--------|:---------|:----------|
|choiceID|Integer|true|minvalue: 0<br>maxvalue: 65535||
|menuName|String|false|maxlength: 500||
|image|Common.Image|false|||
|secondaryText|String|false|maxlength: 500||
|tertiaryText|String|false|maxlength: 500||
|secondaryImage|Image|false|||

### DeviceStatus

|Name|Type|Mandatory|Additional|Description|
|:---|:---|:--------|:---------|:----------|
|voiceRecOn|Boolean|false|||
|btIconOn|Boolean|false|||
|callActive|Boolean|false|||
|phoneRoaming|Boolean|false|||
|textMsgAvailable|Boolean|false|||
|battLevelStatus|Common.DeviceLevelStatus|false|||
|stereoAudioOutputMuted|Boolean|false|||
|monoAudioOutputMuted|Boolean|false|||
|signalLevelStatus|Common.DeviceLevelStatus|false|||
|primaryAudioSource|Common.PrimaryAudioSource|false|||
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
|compassDirection|Common.CompassDirection|false|||
|pdop|Float|false|minvalue: 0<br>maxvalue: 1000||
|hdop|Float|false|minvalue: 0<br>maxvalue: 1000||
|vdop|Float|false|minvalue: 0<br>maxvalue: 1000||
|actual|Boolean|false|||
|satellites|Integer|false|minvalue: 0<br>maxvalue: 31||
|dimension|Common.Dimension|false|||
|altitude|Float|false|minvalue: -10000<br>maxvalue: 10000||
|heading|Float|false|minvalue: 0<br>maxvalue: 359.99||
|speed|Float|false|minvalue: 0<br>maxvalue: 500||

### SingleTireStatus

|Name|Type|Mandatory|Additional|Description|
|:---|:---|:--------|:---------|:----------|
|status|Common.ComponentVolumeStatus|true|||
|tpms|[Common.TPMS](../enums/#tpms)|false||The status of TPMS according to the particular tire.|
|pressure|Float|false|minvalue: 0<br>maxvalue: 2000|The pressure value of the particular tire in kilopascals.|

### SoftButtonCapabilities

|Name|Type|Mandatory|Additional|Description|
|:---|:---|:--------|:---------|:----------|
|shortPressAvailable|Boolean|true|||
|longPressAvailable|Boolean|true|||
|upDownAvailable|Boolean|true|||
|imageSupported|Boolean|true|||

### HMIApplication

|Name|Type|Mandatory|Additional|Description|
|:---|:---|:--------|:---------|:----------|
|appName|String|true|maxlength: 100||
|ngnMediaScreenAppName|String|false|maxlength: 100||
|icon|String|false|||
|deviceInfo|Common.DeviceInfo|true|||
|secondaryDeviceInfo|Common.DeviceInfo|true||The ID, serial number, transport type that are acquired through Secondary Transport.|
|policyAppID|String|true|minlength: 1<br>maxlength: 50||
|ttsName|Common.TTSChunk|false|array: true<br>minsize: 1<br>maxsize: 100||
|vrSynonyms|String|false|array: true<br>minsize: 1<br>maxsize: 100<br>maxlength: 40||
|appID|Integer|true||Must not interfere with any name of previously registered applications from the same device|
|hmiDisplayLanguageDesired|Common.Language|false|||
|isMediaApplication|Boolean|false|||
|appType|Common.AppHMIType|false|array: true<br>minsize: 1<br>maxsize: 100||
|greyOut|Boolean|false|||
|requestType|Common.RequestType|false|array: true<br>minsize: 0<br>maxsize: 100||
|requestSubType|String|false|array:true <br> minsize:0 <br>maxsize:100 <br> maxlength:100|The list of SystemRequest's requestSubTypes allowed by policies for the named application.<br>If the app sends a requestSubType which is not specified in this list, then that request should be rejected.<br>An empty array signifies that any value of requestSubType is allowed for this app. <br> If this parameter is omitted, then a request with any value of requestSubType is now allowed for this app|
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
|name|Common.ButtonName|true|||
|shortPressAvailable|Boolean|true|||
|longPressAvailable|Boolean|true|||
|upDownAvailable|Boolean|true|||

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
|ignitionStableStatus|Common.IgnitionStableStatus|true|||
|ignitionStatus|Common.IgnitionStatus|true|||
|driverDoorAjar|Boolean|false|||
|passengerDoorAjar|Boolean|false|||
|rearLeftDoorAjar|Boolean|false|||
|rearRightDoorAjar|Boolean|false|||

### BeltStatus

|Name|Type|Mandatory|Additional|Description|
|:---|:---|:--------|:---------|:----------|
|driverBeltDeployed|Common.VehicleDataEventStatus|false|||
|passengerBeltDeployed|Common.VehicleDataEventStatus|false|||
|passengerBuckleBelted|Common.VehicleDataEventStatus|false|||
|driverBuckleBelted|Common.VehicleDataEventStatus|false|||
|leftRow2BuckleBelted|Common.VehicleDataEventStatus|false|||
|passengerChildDetected|Common.VehicleDataEventStatus|false|||
|rightRow2BuckleBelted|Common.VehicleDataEventStatus|false|||
|middleRow2BuckleBelted|Common.VehicleDataEventStatus|false|||
|middleRow3BuckleBelted|Common.VehicleDataEventStatus|false|||
|leftRow3BuckleBelted|Common.VehicleDataEventStatus|false|||
|rightRow3BuckleBelted|Common.VehicleDataEventStatus|false|||
|leftRearInflatableBelted|Common.VehicleDataEventStatus|false|||
|rightRearInflatableBelted|Common.VehicleDataEventStatus|false|||
|middleRow1BeltDeployed|Common.VehicleDataEventStatus|false|||
|middleRow1BuckleBelted|Common.VehicleDataEventStatus|false|||

### Turn

|Name|Type|Mandatory|Additional|Description|
|:---|:---|:--------|:---------|:----------|
|navigationText|Common.TextFieldStruct|false|||
|turnIcon|Common.Image|false|||

### EmergencyEvent

|Name|Type|Mandatory|Additional|Description|
|:---|:---|:--------|:---------|:----------|
|emergencyEventType|Common.EmergencyEventType||||
|fuelCutoffStatus|Common.FuelCutoffStatus||||
|rolloverEvent|Common.VehicleDataEventStatus||||
|maximumChangeVelocity|Common.VehicleDataEventStatus||||
|multipleEvents|Common.VehicleDataEventStatus||||

### VehicleDataResult

|Name|Type|Mandatory|Additional|Description|
|:---|:---|:--------|:---------|:----------|
|dataType|Common.VehicleDataType||||
|resultCode|Common.VehicleDataResultCode||||

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
|fieldName|Common.TextFieldName|true| |The name of the field for displaying the text.|
|fieldText|String|true|maxlength: 500|The data contained in the field.|
|fieldType|Common.MetadataType|false|array: true<br>minSize: 0<br>maxSize: 5|The type of data contained in the field.|

### DeviceInfo

|Name|Type|Mandatory|Additional|Description|
|:---|:---|:--------|:---------|:----------|
|name|String|true|||
|id|String|true|||
|transportType|Common.TransportType|false|||
|isSDLAllowed|Boolean|false|||

### SoftButton

|Name|Type|Mandatory|Additional|Description|
|:---|:---|:--------|:---------|:----------|
|type|Common.SoftButtonType|true|||
|text|String|false|maxlength: 500||
|image|Common.Image|false|||
|isHighlighted|Boolean|false|||
|softButtonID|Integer|true|minvalue: 0<br>maxvalue: 65535||
|systemAction|Common.SystemAction|true|||

### AirbagStatus

|Name|Type|Mandatory|Additional|Description|
|:---|:---|:--------|:---------|:----------|
|driverAirbagDeployed|Common.VehicleDataEventStatus||||
|driverSideAirbagDeployed|Common.VehicleDataEventStatus||||
|driverCurtainAirbagDeployed|Common.VehicleDataEventStatus||||
|passengerAirbagDeployed|Common.VehicleDataEventStatus||||
|passengerCurtainAirbagDeployed|Common.VehicleDataEventStatus||||
|driverKneeAirbagDeployed|Common.VehicleDataEventStatus||||
|passengerSideAirbagDeployed|Common.VehicleDataEventStatus||||
|passengerKneeAirbagDeployed|Common.VehicleDataEventStatus||||

### RGBColor

|Name|Type|Mandatory|Additional|Description|
|:---|:---|:--------|:---------|:----------|
|red|Integer|true|minvalue: 0<br>maxvalue: 255||
|green|Integer|true|minvalue: 0<br>maxvalue: 255||
|blue|Integer|true|minvalue: 0<br>maxvalue: 255||

### TemplateColorScheme

|Name|Type|Mandatory|Additional|Description|
|:---|:---|:--------|:---------|:----------|
|primaryColor|Common.RGBColor|true|||
|secondaryColor|Common.RGBColor|true|||
|backgroundColor|Common.RGBColor|true|||

### DisplayCapabilities

|Name|Type|Mandatory|Additional|Description|
|:---|:---|:--------|:---------|:----------|
|displayType|Common.DisplayType|true|||
|displayName|String|true||The name of the display the app is connected to.|
|textFields|Common.TextField|true|array: true<br>minsize: 0<br>maxsize: 100||
|imageFields|Common.ImageField|false|array: true<br>minsize: 1<br>maxsize: 100||
|mediaClockFormats|Common.MediaClockFormat|true|array: true<br>minsize: 0<br>maxsize: 100||
|imageCapabilities|Common.ImageType|false|array: true<br>minsize: 0<br>maxsize: 2||
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
|imageType|Common.ImageType|true||Describes whether it is a static or dynamic image.|
|isTemplate|Boolean|false||Optional value to specify whether it's a template image. A template image can be (re)colored by the HMI as needed by using an image pattern.|

### MyKey

|Name|Type|Mandatory|Additional|Description|
|:---|:---|:--------|:---------|:----------|
|e911Override|Common.VehicleDataStatus|true|||

### ImageField

|Name|Type|Mandatory|Additional|Description|
|:---|:---|:--------|:---------|:----------|
|name|Common.ImageFieldName|true|||
|imageTypeSupported|Common.FileType|false|array: true<br>minsize: 1<br>maxsize: 100||
|imageResolution|Common.ImageResolution|false|||

### VideoConfig

|Name|Type|Mandatory|Additional|Description|
|:---|:---|:--------|:---------|:----------|
|protocol|Common.VideoStreamingProtocol|false| |The video protocol configuration.|
|codec|Common.VideoStreamingCodec|false| |The video codec configuration.|
|width|Integer|false| |Width of the video stream, in pixels.|
|height|Integer|false| |Height of the video stream, in pixels.|

### ExternalConsentStatus
|Name|Type|Mandatory|Additional|Description|
|:---|:---|:--------|:---------|:----------|
|entityType|Integer|true|minvalue: 0<br>maxvalue: 128|The entityType which status is informed by "status" param.|
|entityID|Integer|true|minvalue: 0<br>maxvalue: 128|The corresponding ID of entityType which status is informed by "status" param.|
|status|Common.EntityStatus|true|-|Status of External User Consent Settings entity: "ON" or "OFF"|

### ModuleData

|Name|Type|Mandatory|Additional|Description|
|:---|:---|:--------|:---------|:----------|
|moduleType|Common.ModuleType|true||The moduleType indicates which type of data should be changed and identifies which data object exists in this struct. For example, if the moduleType is CLIMATE then a "climateControlData" should exist|
|radioControlData|Common.RadioControlData|false|||
|climateControlData|Common.ClimateControlData|false|||
|audioControlData|Common.AudioControlData|false|||
|lightControlData|Common.LightControlData|false|||
|hmiSettingsControlData|Common.HMISettingsControlData|false|||

### RadioControlData

|Name|Type|Mandatory|Additional|Description|
|:---|:---|:--------|:---------|:----------|
|frequencyInteger|Integer|false|minvalue:0 maxvalue:1710|The integer part of the frequency ie for 101.7 this value should be 101|
|frequencyFraction|Integer|false|minvalue:0 maxvalue:9|The fractional part of the frequency for 101.7 is 7|
|band|Common.RadioBand|false|||
|rdsData|Common.RdsData|false|||
|availableHDs|Integer|false|minvalue:1 maxvalue:7|number of HD sub-channels if available|
|hdChannel|Integer|false|minvalue:1 maxvalue:7|Current HD sub-channel if available|
|signalStrength|Integer|false|minvalue:0 maxvalue:100||
|signalChangeThreshold|Integer|false|minvalue:0 maxvalue:100|If the signal strength falls below the set value for this parameter, the radio will tune to an alternative frequency|
|radioEnable|Boolean|false||True if the radio is on, false is the radio is off|
|state|Common.RadioState|false||||
|sisData|Common.SisData|false||Read-only Station Information Service (SIS) data provides basic information about the station such as call sign, as well as information not displayable to the consumer such as the station identification number|
|hdRadioEnable|Boolean|false||True if the hd radio is on, false is the radio is off|

### RdsData

|Name|Type|Mandatory|Additional|Description|
|:---|:---|:--------|:---------|:----------|
|PS|String|false|minlength:0<br>maxlength:8|Program Service Name|
|RT|String|false|minlength:0<br>maxlength:64|Radio Text|
|CT|String|false|minlength:24 maxlength:24|The clock text in UTC format as YYYY-MM-DDThh:mm:ss.sTZD|
|PI|String|false|minlength:0 maxlength:6|Program Identification - the call sign for the radio station|
|PTY|Integer|false|minvalue:0 maxvalue:31|The program type - The region should be used to differentiate between EU and North America program types|
|TP|Boolean|false||Traffic Program Identification - Identifies a station that offers traffic|
|TA|Boolean|false||Traffic Announcement Identification - Indicates an ongoing traffic announcement|
|REG|String|false||Region|

### StationIDNumber
|Name|Type|Mandatory|Additional|Description|
|:---|:---|:--------|:---------|:----------|
|countryCode|Integer|false|minvalue="0" <br> maxvalue="999"|Binary Representation of ITU Country Code. USA Code is 001.|
|fccFacilityId|Integer|false|minvalue="0" <br> maxvalue="999999"|Binary representation  of unique facility ID assigned by the FCC; FCC controlled for U.S. territory|

### SisData
|Name|Type|Mandatory|Additional|Description|
|:---|:---|:--------|:---------|:----------|
|stationShortName|String|false|minlength="4" <br> maxlength="7"|Identifies the 4-alpha-character station call sign plus an optional (-FM) extension|
|stationIDNumber|Common.StationIDNumber|false||Used for network Application. Consists of Country Code and FCC Facility ID.|
|stationLongName|String|false|minlength="0" <br> maxlength="56"|Identifies the station call sign or other identifying information in the long format.|
|stationLocation|Common.GPSData|false||Provides the 3-dimensional geographic station location.|
|stationMessage|String|false|minlength="0" <br> maxlength="56"|May be used to convey textual information of general interest to the consumer such as weather forecasts or public service announcements. <br> Includes a high priority delivery feature to convey emergencies that may be in the listening area.|

### ClimateControlData

|Name|Type|Mandatory|Additional|Description|
|:---|:---|:--------|:---------|:----------|
|fanSpeed|Integer|false|minvalue: 0 <br> maxvalue: 100||
|currentTemperature|Temperature|false|||
|desiredTemperature|Temperature|false|||
|acEnable|Boolean|false|||
|circulateAirEnable|Boolean|false|||
|autoModeEnable|Boolean|false|||
|defrostZone|DefrostZone|false|||
|dualModeEnable|Boolean|false|||
|acMaxEnable|Boolean|false|||
|ventilationMode|VentilationMode|false|||
|heatedSteeringWheelEnable|Boolean|false||value false means disabled/turn off, value true means enabled/turn on.|
|heatedWindshieldEnable|Boolean|false||value false means disabled, value true means enabled.|
|heatedRearWindowEnable|Boolean|false||value false means disabled, value true means enabled.|
|heatedMirrorsEnable|Boolean|false||value false means disabled, value true means enabled.|

### Temperature

|Name|Type|Mandatory|Additional|Description|
|:---|:---|:--------|:---------|:----------|
|unit|TemperatureUnit|true||Temperature Unit|
|value|Float|true||The temperature value is in TemperatureUnit specified unit|

### RemoteControlCapabilities

|Name|Type|Mandatory|Additional|Description|
|:---|:---|:--------|:---------|:----------|
|climateControlCapabilities|ClimateControlCapabilities|false|array: true <br> minsize: 1 <br> maxsize: 100|If included, the platform supports RC climate controls. For this baseline version, maxsize=1. i.e. only one climate control module is supported|
|radioControlCapabilities|RadioControlCapabilities|false|array: true <br> minsize: 1 <br> maxsize: 100|If included, the platform supports RC radio controls. For this baseline version, maxsize=1. i.e. only one climate control module is supported|
|seatControlCapabilities|Common.SeatControlCapabilities|false|minsize="1" <br> maxsize="100" <br> array="true"|If included, the platform supports seat controls|
|buttonCapabilities|Common.ButtonCapabilities|false|array: true <br> minsize: 1 <br> maxsize: 100|If included, the platform supports RC button controls with the included button names|
|seatControlCapabilities|Common.SeatControlCapabilities|false|minsize="1" <br> maxsize="100" <br> array="true"|If included, the platform supports seat controls.|
|audioControlCapabilities|Common.AudioControlCapabilities|false| minsize="1" <br> maxsize="100" <br> array="true"| If included, the platform supports audio controls.|
|hmiSettingsControlCapabilities|Common.HMISettingsControlCapabilities|false||If included, the platform supports hmi setting controls.|
|lightControlCapabilities|Common.LightControlCapabilities|false||If included, the platform supports light controls.|

### ClimateControlCapabilities
|Name|Type|Mandatory|Additional|Description|
|:---|:---|:--------|:---------|:----------|
|moduleName|String|true|maxlength: 100|The short friendly name of the climate control module. It should not be used to identify a module by mobile application.|
|fanSpeedAvailable|Boolean|false||Availability of the control of fan speed <br> True: Available, False: Not Available, Not present: Not Available.|
|desiredTemperatureAvailable|Boolean|false||Availability of the control of desired temperature. <br> True: Available, False: Not Available, Not present: Not Available.|
|acEnableAvailable|Boolean|false||Availability of the control of turn on/off AC. <br> True: Available, False: Not Available, Not present: Not Available.|
|acMaxEnableAvailable|Boolean|false||Availability of the control of enable/disable air conditioning is ON on the maximum level. <br> True: Available, False: Not Available, Not present: Not Available.|
|circulateAirEnableAvailable|Boolean|false||Availability of the control of enable/disable circulate Air mode. <br> True: Available, False: Not Available, Not present: Not Available.|
|autoModeEnableAvailable|Boolean|false||Availability of the control of enable/disable auto mode. <br> True: Available, False: Not Available, Not present: Not Available.|
|dualModeEnableAvailable|Boolean|false||Availability of the control of enable/disable dual mode. <br> True: Available, False: Not Available, Not present: Not Available.|
|defrostZoneAvailable|Boolean|false||Availability of the control of defrost zones. <br> True: Available, False: Not Available, Not present: Not Available.|
|defrostZone|DefrostZone|false|array: true <br> minsize: 1 <br> maxsize: 100|A set of all defrost zones that are controllable.|
|ventilationModeAvailable|Boolean|false|| Availability of the control of air ventilation mode. <br> True: Available, False: Not Available, Not present: Not Available.|
|ventilationMode|VentilationMode|false|array: true <br> minsize: 1 <br> maxsize: 100|A set of all ventilation modes that are controllable|
|heatedSteeringWheelAvailable|Boolean|false|| Availability of the control (enable/disable) of heated Steering Wheel. <br> True: Available, False: Not Available, Not present: Not Available.|
|heatedWindshieldAvailable|Boolean|false|| Availability of the control (enable/disable) of heated Windshield. <br> True: Available, False: Not Available, Not present: Not Available.|
|heatedRearWindowAvailable|Boolean|false|| Availability of the control (enable/disable) of heated Rear Window. <br> True: Available, False: Not Available, Not present: Not Available.|
|heatedMirrorsAvailable|Boolean|false|| Availability of the control (enable/disable) of heated Mirrors. <br> True: Available, False: Not Available, Not present: Not Available.|

### AudioControlCapabilities

|Name|Type|Mandatory|Additional|Description|
|:---|:---|:--------|:---------|:----------|
|moduleName|String|true|maxlength="100"|The short friendly name of the light control module. <br> It should not be used to identify a module by mobile application.|
|sourceAvailable|Boolean|false||Availability of the control of audio source.|
|keepContextAvailable|Boolean|false||Availability of the parameter keepContext.|
|volumeAvailable|Boolean|false||Availability of the control of audio volume.|
|equalizerAvailable|Boolean|false||Availability of the control of Equalizer Settings.|
|equalizerMaxChannelId|Integer|false|minvalue="1" <br> maxvalue="100"|Must be included if equalizerAvailable=true, and assume all IDs starting from 1 to this value are valid.|

### EqualizerSettings

|Name|Type|Mandatory|Additional|Description|
|:---|:---|:--------|:---------|:----------|
|channelId|Integer|true|minvalue="1" <br> maxvalue="100"|Defines the each Equalizer channel settings.|
|channelName|String|false|maxlength="50"|Read-only channel / frequency name (e.i. "Treble, Midrange, Bass" or "125 Hz")|
|channelSetting|Integer|true|minvalue="0" <br> maxvalue="100"|Reflects the setting, from 0%-100%.|


### AudioControlData

|Name|Type|Mandatory|Additional|Description|
|:---|:---|:--------|:---------|:----------|
|source|Common.PrimaryAudioSource|false||In a getter response or a notification, it is the current primary audio source of the system. <br> In a setter request, it is the target audio source that the system shall switch to. <br> If the value is MOBILE_APP, the system shall switch to the mobile media app that issues the setter RPC.|
|keepContext|Boolean|false||This parameter shall not be present in any getter responses or notifications. <br> This parameter is optional in a setter request. The default value is false. <br> If it is false, the system not only changes the audio source but also brings the default infotainment system UI associated with the audio source to foreground and set the application to background. <br> If it is true, the system changes the audio source, but keeps the current application's context.|
|volume|Integer|false|minvalue="0" <br> maxvalue="100"|Reflects the volume of audio, from 0%-100%."
|equalizerSettings|Common.EqualizerSettings|false|minvalue="1" <br> maxvalue="100"<br>array ="true"|Defines the list of supported channels (band) and their current/desired settings on HMI|


### LightCapabilities

|Name|Type|Mandatory|Additional|Description|
|:---|:---|:--------|:---------|:----------|
|name|Common.LightName|true|||
|statusAvailable|Boolean|false||Indicates if the status (ON/OFF) can be set remotely. App shall not use read-only values (RAMP_UP/RAMP_DOWN/UNKNOWN/INVALID) in a setInteriorVehicleData request.|
|densityAvailable|Boolean|false||Indicates if the light's density can be set remotely (similar to a dimmer).|
|RGBColorSpaceAvailable|Boolean|false||Indicates if the light's color can be set remotely by using the sRGB color space.|

### LightControlCapabilities

|Name|Type|Mandatory|Additional|Description|
|:---|:---|:--------|:---------|:----------|
|moduleName|String|true|maxlength="100"|The short friendly name of the light control module. <br> It should not be used to identify a module by mobile application.|
|supportedLights|Common.LightCapabilities|true|minsize="1" <br> maxsize="100" <br> array="true"| An array of available LightCapabilities that are controllable.|


### LightState

|Name|Type|Mandatory|Additional|Description|
|:---|:---|:--------|:---------|:----------|
|id|Common.LightName|true||The name of a light or a group of lights.|
|status|Common.LightName|true|||
|density|Float|false|minvalue="0" <br> maxvalue="1"||
|color|Common.RGBColor|false|||


### LightControlData

|Name|Type|Mandatory|Additional|Description|
|:---|:---|:--------|:---------|:----------|
|lightState|Common.LightState|true|minsize="1" <br> maxsize="100" <br> array="true"|An array of LightNames and their current or desired status. <br> Status of the LightNames that are not listed in the array shall remain unchanged.|


### HMISettingsControlCapabilities

|Name|Type|Mandatory|Additional|Description|
|:---|:---|:--------|:---------|:----------|
|moduleName|String|true|maxlength="100"|The short friendly name of the hmi setting module. <br> It should not be used to identify a module by mobile application.|
|distanceUnitAvailable|Boolean|false||Availability of the control of distance unit.|
|temperatureUnitAvailable|Boolean|false||Availability of the control of temperature unit.|
|displayModeUnitAvailable|Boolean|false||Availability of the control of HMI display mode.|


### HMISettingsControlData

|Name|Type|Mandatory|Additional|Description|
|:---|:---|:--------|:---------|:----------|
|displayMode|Common.DisplayMode|false||
|temperatureUnit|Common.TemperatureUnit|false||
|distanceUnit|Common.DistanceUnit|false||

### RadioControlCapabilities

|Name|Type|Mandatory|Additional|Description|
|:---|:---|:--------|:---------|:----------|
|moduleName|String|true|maxlength: 100| The short friendly name of the climate control module. <br> It should not be used to identify a module by mobile application.|
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

### ExternalConsentStatus

|Name|Type|Mandatory|Additional|Description|
|:---|:---|:--------|:---------|:----------|
|entityType|Integer|true|minvalue: 0<br>maxvalue: 128|The entityType which status is informed by "status" param.|
|entityID|Integer|true|minvalue: 0<br>maxvalue: 128|The corresponding ID of entityType which status is informed by "status" param.|
|status|Common.EntityStatus|true|-|Status of External User Consent Settings entity: "ON" or "OFF"|

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
|id|Integer|true|minvalue: 0<br>maxvalue: 128|A unique identifier for the haptic rectangle|
|rect|Common.Rectangle|true| |The position of the haptic rectangle to be highlighted.<br>The center of this rectangle is considered "touched" when the element is focused and then selected.|

### FuelRange  
|Name|Type|Mandatory|Additional|Description|
|:---|:---|:--------|:---------|:----------|  
|type|FuelType|false|||
|range|Float|faslse|minvalue=0<br>maxvalue=10000|The estimate range in KM the vehicle can travel based on fuel level and consumption|

### MassageModeData

|Name|Type|Mandatory|Additional|Description|
|:---|:---|:--------|:---------|:----------|
|massageZone|Common.MassageZone|true|||
|massageMode|Common.MassageMode|true||

### MassageCushionFirmness

|Name|Type|Mandatory|Additional|Description|
|:---|:---|:--------|:---------|:----------|
|cushion|Common.MassageCushion|true||
|firmness|Integer|true|minvalue="0" <br> maxvalue="100"||

### SeatMemoryAction

|Name|Type|Mandatory|Additional|Description|
|:---|:---|:--------|:---------|:----------|
|id|Integer|true|minvalue="1" <br> maxvalue="10" ||
|label|String|false|maxlength="100"||
|action|Common.SeatMemoryActionType|true|||

### SeatControlData

|Name|Type|Mandatory|Additional|Description|
|:---|:---|:--------|:---------|:----------|
|id|Common.SupportedSeat|true|||
|heatingEnabled|Boolean|false||
|coolingEnabled|Boolean|false||
|heatingLevel|Integer|false|minvalue="0" <br> maxvalue="100"||
|coolingLevel|Integer|false|minvalue="0" <br> maxvalue="100"||
|horizontalPosition|Integer|false|minvalue="0" maxvalue="100"||
|verticalPosition|Integer|false|minvalue="0" maxvalue="100"||
|frontVerticalPosition|Integer|false|minvalue="0" <br> maxvalue="100"||
|backVerticalPosition|Integer|false|minvalue="0" <br> maxvalue="100"||
|backTiltAngle|Integer|false|minvalue="0" <br> maxvalue="100"||
|headSupportHorizontalPosition|Integer|false|minvalue="0" <br> maxvalue="100"||
|headSupportVerticalPosition|Integer|false|minvalue="0" <br> maxvalue="100"||
|massageEnabled|Boolean|false|||
|massageMode|Common.MassageModeData|true|minsize="1" <br> maxsize="2" <br> array="true"||
|massageCushionFirmness|Common.MassageCushionFirmness|false|minsize="1" <br> maxsize="5" <br> array="true"||
|memory|Common.SeatMemoryAction|false|||

### SeatControlCapabilities

|Name|Type|Mandatory|Additional|Description|
|:---|:---|:--------|:---------|:----------|
|moduleName|String|true|maxlength="100"|The short friendly name of the light control module. <br> It should not be used to identify a module by mobile application.|
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
|millisecond|Integer|false|minvalue: 0<br> maxvalue: 999|Milliseconds – part of time - one thousandth split second|
|seconds|Integer|false|minvalue: 0<br> maxvalue: 60|Seconds part of time|
|minutes|Integer|false|minvalue: 0<br> maxvalue: 59|Minutes part of time|
|hour|Integer|false|minvalue: 0<br> maxvalue: 23|Hours part of time. Note that this structure accepts time only in 24 Hr format|
|day|Integer|false|minvalue: 1 <br>maxvalue: 31|Day of the month|
|month|Integer|false|minvalue: 1<br> maxvalue: 12|Month of the year|
|year|Integer|false|minvalue: 0 <br>maxvalue: 4095|The year in YYYY format|
|tz_hour|Integer|false|minvalue: -12 <br> maxvalue: 14 <br> defvalue: 0|Time zone offset in Hours with regard to UTC.|
|tz_minute|Integer|false|minvalue: 0 <br>maxvalue: 59 <br> defvalue: 0|Time zone offset in Min with regard to UTC.|

### OASISAddress

|Name|Type|Mandatory|Additional|Description|
|:---|:---|:--------|:---------|:----------|
|countryName|String|false|minlength="0"<br>maxlength="200"|Name of the country (localized)|
|countryCode|String|false|minlength="0"<br>maxlength="200"|Name of country (ISO 3166-2)|
|postalCode|String|false|minlength="0"<br>maxlength="200"|(PLZ, ZIP, PIN, CAP etc.)|
|administrativeArea|String|false|minlength="0"<br>maxlength="200"|Portion of country (e.g. state)|
|subAdministrativeAre|String|false|minlength="0"<br>maxlength="200"|Portion of administrativeArea (e.g. county)|
|locality|String|false|minlength="0"<br>maxlength="200"|Hypernym for city/village|
|subLocality|String|false|minlength="0"<br>maxlength="200"|Hypernym for district|
|thoroughfare|String|false|minlength="0"<br>maxlength="200"|Hypernym for street, road etc|
|subThoroughfare|String|false|minlength="0"<br>maxlength="200"|Portion of thoroughfare (e.g. house number)|

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
|allowAppConsumers|Boolean|false|defvalue: false|If true, app service consumers beyond the IVI system will be able to access this service. If false, only the IVI system will be able consume the service. If not provided, it is assumed to be false|
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

### MediaServiceManifest

There are no defined parameters for this struct.

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
|regions|String|false|array: true<br>minsize: 1<br> maxsize: 99||
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
|bearing|Integer|false|minvalue: 0<br>maxvalue:359|The angle at which this instruction takes place. For example, 0 would mean straight, less than 45 is bearing right, greater than 135 is sharp right, between 45 and 135 is a regular right, and 180 is a U-Turn, etc|
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
|nextInstructionDistance|Float|false||The distance to this instruction from current location. This should only be updated ever .1 unit of distance. For more accuracy the consumer can use the GPS location of itself and the next instruction|
|nextInstructionDistanceScale|Float|false||Distance till next maneuver (starting from) from previous maneuver|
|prompt|String|false||This is a prompt message that should be conveyed to the user through either display or voice (TTS). This param will change often as it should represent the following: approaching instruction, post instruction, alerts that affect the current navigation session, etc|