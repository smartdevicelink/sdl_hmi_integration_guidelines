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
|dialNumberEnabled|Boolean|false||If the module has the abiulity to perform dial number|

### SystemCapabilities

|Name|Type|Mandatory|Additional|Description|
|:---|:---|:--------|:---------|:----------|
|navigationCapability|Boolean|false|||
|phoneCapability|Boolean|false|||

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
|text|String|true|maxlength: 500||
|type|Common.SpeechCapabilities|true|||

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
|longitudeDegrees|Float|false|minvalue: -180<br>maxvalue: 180||
|latitudeDegrees|Float|false|minvalue: -90<br>maxvalue: 90||
|utcYear|Integer|false|minvalue: 2010<br>maxvalue: 2100||
|utcMonth|Integer|false|minvalue: 1<br>maxvalue: 12||
|utcDay|Integer|false|minvalue: 1<br>maxvalue: 31||
|utcHours|Integer|false|minvalue: 0<br>maxvalue: 23||
|utcMinutes|Integer|false|minvalue: 0<br>maxvalue: 59||
|utcSeconds|Integer|false|minvalue: 0<br>maxvalue: 59||
|compassDirection|Common.CompassDirection|false|||
|pdop|Float|false|minvalue: 0<br>maxvalue: 10||
|hdop|Float|false|minvalue: 0<br>maxvalue: 10||
|vdop|Float|false|minvalue: 0<br>maxvalue: 10||
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
|policyAppID|String|true|minlength: 1<br>maxlength: 50||
|ttsName|Common.TTSChunk|false|array: true<br>minsize: 1<br>maxsize: 100||
|vrSynonyms|String|false|array: true<br>minsize: 1<br>maxsize: 100<br>maxlength: 40||
|appID|Integer|true|||
|hmiDisplayLanguageDesired|Common.Language|false|||
|isMediaApplication|Boolean|false|||
|appType|Common.AppHMIType|false|array: true<br>minsize: 1<br>maxsize: 100||
|greyOut|Boolean|false|||
|requestType|Common.RequestType|false|array: true<br>minsize: 0<br>maxsize: 100||

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

### DisplayCapabilities

|Name|Type|Mandatory|Additional|Description|
|:---|:---|:--------|:---------|:----------|
|displayType|Common.DisplayType|true|||
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
|value|String|true|maxlength: 65535||
|imageType|Common.ImageType|true|||

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
|climateControlData|Common.ClimateControlData|false||

### RadioControlData

|Name|Type|Mandatory|Additional|Description|
|:---|:---|:--------|:---------|:----------|
|frequencyInteger|Integer|false|minvalue:0 maxvalue:1710|The integer part of the frequency ie for 101.7 this value should be 101|
|frequencyFraction|Integer|false|minvalue:0 maxvalue:9|The fractional part of the frequency for 101.7 is 7|
|band|Common.RadioBand|false|||
|rdsData|Common.RdsData|false|||
|availableHDs|Integer|false|minvalue:1 maxvalue:3|number of HD sub-channels if available|
|hdChannel|Integer|false|minvalue:1 maxvalue:3|Current HD sub-channel if available|
|signalStrength|Integer|false|minvalue:0 maxvalue:100||
|signalChangeThreshold|Integer|false|minvalue:0 maxvalue:100|If the signal strength falls below the set value for this parameter, the radio will tune to an alternative frequency|
|radioEnable|Boolean|false||True if the radio is on, false is the radio is off|
|state|Common.RadioState|false||||

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
|ButtonCapabilities|false|array: true <br> minsize: 1 <br> maxsize: 100|If included, the platform supports RC button controls with the included button names|

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

### ExternalConsentStatus
|Name|Type|Mandatory|Additional|Description|
|:---|:---|:--------|:---------|:----------|
|entityType|Integer|true|minvalue: 0<br>maxvalue: 128|The entityType which status is informed by "status" param.|
|entityID|Integer|true|minvalue: 0<br>maxvalue: 128|The corresponding ID of entityType which status is informed by "status" param.|
|status|Common.EntityStatus|true|-|Status of External User Consent Settings entity: "ON" or "OFF"|
