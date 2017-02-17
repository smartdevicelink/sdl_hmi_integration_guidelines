## Enumerations

### KeyboardEvent

|Name|Value|Description|
|:---|:----|:----------|
|KEYPRESS|0||
|ENTRY_SUBMITTED|1||
|ENTRY_VOICE|2||
|ENTRY_CANCELLED|3||
|ENTRY_ABORTED|4||

### FuelCutoffStatus

|Name|Value|Description|
|:---|:----|:----------|
|TERMINATE_FUEL|0||
|NORMAL_OPERATION|1||
|FAULT|2||

### TransportType

|Name|Value|Description|
|:---|:----|:----------|
|BLUETOOTH|0||
|USB|1||
|WIFI|2||

### ButtonPressMode

|Name|Value|Description|
|:---|:----|:----------|
|LONG|0||
|SHORT|1||

### VRCommandType

|Name|Value|Description|
|:---|:----|:----------|
|Choice|0||
|Command|1||

### AppHMIType

|Name|Value|Description|
|:---|:----|:----------|
|DEFAULT|0||
|COMMUNICATION|1||
|MEDIA|2||
|MESSAGING|3||
|NAVIGATION|4||
|INFORMATION|5||
|SOCIAL|6||
|BACKGROUND_PROCESS|7||
|TESTING|8||
|SYSTEM|9||

### SpeechCapabilities

|Name|Value|Description|
|:---|:----|:----------|
|TEXT|0||
|SAPI_PHONEMES|1||
|LHPLUS_PHONEMES|2||
|PRE_RECORDED|3||
|SILENCE|4||

### TextFieldName

|Name|Value|Description|
|:---|:----|:----------|
|mainField1|0||
|mainField2|1||
|mainField3|2||
|mainField4|3||
|statusBar|4||
|mediaClock|5||
|mediaTrack|6||
|alertText1|7||
|alertText2|8||
|alertText3|9||
|scrollableMessageBody|10||
|initialInteractionText|11||
|navigationText1|12||
|navigationText2|13||
|ETA|14||
|totalDistance|15||
|audioPassThruDisplayText1|16||
|audioPassThruDisplayText2|17||
|sliderHeader|18||
|sliderFooter|19||
|menuName|20||
|secondaryText|21||
|tertiaryText|22||
|menuTitle|23||
|navigationText|24||
|notificationText|25||
|locationName|26||
|locationDescription|27||
|addressLines|28||
|phoneNumber|29||
|timeToDestination|30||
|turnText|31||

### AmbientLightStatus

|Name|Value|Description|
|:---|:----|:----------|
|NIGHT|0||
|TWILIGHT_1|1||
|TWILIGHT_2|2||
|TWILIGHT_3|3||
|TWILIGHT_4|4||
|DAY|5||
|UNKNOWN|6||
|INVALID|7||

### StatisticsType

|Name|Value|Description|
|:---|:----|:----------|
|iAPP_BUFFER_FULL|0||

### VehicleDataEventStatus

|Name|Value|Description|
|:---|:----|:----------|
|NO_EVENT|0||
|NO|1||
|YES|2||
|NOT_SUPPORTED|3||
|FAULT|4||

### KeyboardLayout

|Name|Value|Description|
|:---|:----|:----------|
|QWERTY|0||
|QWERTZ|1||
|AZERTY|2||

### ButtonEventMode

|Name|Value|Description|
|:---|:----|:----------|
|BUTTONUP|0||
|BUTTONDOWN|1||

### VrCapabilities

|Name|Value|Description|
|:---|:----|:----------|
|TEXT|0||

### TextAlignment

|Name|Value|Description|
|:---|:----|:----------|
|LEFT_ALIGNED|0||
|RIGHT_ALIGNED|1||
|CENTERED|2||

### DeviceState

|Name|Value|Description|
|:---|:----|:----------|
|UNKNOWN|0||
|UNPAIRED|1||

### SystemContext

|Name|Value|Description|
|:---|:----|:----------|
|MAIN|0||
|VRSESSION|1||
|MENU|2||
|HMI_OBSCURED|3||
|ALERT|4||

### SoftButtonType

|Name|Value|Description|
|:---|:----|:----------|
|TEXT|0||
|IMAGE|1||
|BOTH|2||

### DriverDistractionState

|Name|Value|Description|
|:---|:----|:----------|
|DD_ON|0||
|DD_OFF|1||

### MethodName

|Name|Value|Description|
|:---|:----|:----------|
|ALERT|0||
|SPEAK|1||
|AUDIO_PASS_THRU|2||
|ALERT_MANEUVER|3||

### CharacterSet

|Name|Value|Description|
|:---|:----|:----------|
|TYPE2SET|0||
|TYPE5SET|1||
|CID1SET|2||
|CID2SET|3||

### DeactivateReason

|Name|Value|Description|
|:---|:----|:----------|
|AUDIO|0||
|PHONECALL|1||
|NAVIGATIONMAP|2||
|PHONEMENU|3||
|SYNCSETTINGS|4||
|GENERAL|5||

### SamplingRate

|Name|Value|Description|
|:---|:----|:----------|
|8KHZ|0||
|16KHZ|1||
|22KHZ|2||
|44KHZ|3||

### PrerecordedSpeech

|Name|Value|Description|
|:---|:----|:----------|
|HELP_JINGLE|0||
|INITIAL_JINGLE|1||
|LISTEN_JINGLE|2||
|POSITIVE_JINGLE|3||
|NEGATIVE_JINGLE|4||

### MediaClockFormat

|Name|Value|Description|
|:---|:----|:----------|
|CLOCK1|0||
|CLOCK2|1||
|CLOCK3|2||
|CLOCKTEXT1|3||
|CLOCKTEXT2|4||
|CLOCKTEXT3|5||
|CLOCKTEXT4|6||

### TouchType

|Name|Value|Description|
|:---|:----|:----------|
|BEGIN|0||
|MOVE|1||
|END|2||

### HmiZoneCapabilities

|Name|Value|Description|
|:---|:----|:----------|
|FRONT|0||
|BACK|1||

### AlertType

|Name|Value|Description|
|:---|:----|:----------|
|UI|0||
|BOTH|1||

### ECallConfirmationStatus

|Name|Value|Description|
|:---|:----|:----------|
|NORMAL|0||
|CALL_IN_PROGRESS|1||
|CALL_CANCELLED|2||
|CALL_COMPLETED|3||
|CALL_UNSUCCESSFUL|4||
|ECALL_CONFIGURED_OFF|5||
|CALL_COMPLETE_DTMF_TIMEOUT|6||

### ClockUpdateMode

|Name|Value|Description|
|:---|:----|:----------|
|COUNTUP|0||
|COUNTDOWN|1||
|PAUSE|2||
|RESUME|3||
|CLEAR|4||

### DeviceLevelStatus

|Name|Value|Description|
|:---|:----|:----------|
|ZERO_LEVEL_BARS|0||
|ONE_LEVEL_BARS|1||
|TWO_LEVEL_BARS|2||
|THREE_LEVEL_BARS|3||
|FOUR_LEVEL_BARS|4||
|NOT_PROVIDED|5||

### SystemAction

|Name|Value|Description|
|:---|:----|:----------|
|DEFAULT_ACTION|0||
|STEAL_FOCUS|1||
|KEEP_CONTEXT|2||

### ButtonName

|Name|Value|Description|
|:---|:----|:----------|
|OK|0||
|SEEKLEFT|1||
|SEEKRIGHT|2||
|TUNEUP|3||
|TUNEDOWN|4||
|PRESET_0|5||
|PRESET_1|6||
|PRESET_2|7||
|PRESET_3|8||
|PRESET_4|9||
|PRESET_5|10||
|PRESET_6|11||
|PRESET_7|12||
|PRESET_8|13||
|PRESET_9|14||
|CUSTOM_BUTTON|15||
|SEARCH|16||

### KeypressMode

|Name|Value|Description|
|:---|:----|:----------|
|SINGLE_KEYPRESS|0||
|QUEUE_KEYPRESSES|1||
|RESEND_CURRENT_ENTRY|2||

### WiperStatus

|Name|Value|Description|
|:---|:----|:----------|
|OFF|0||
|AUTO_OFF|1||
|OFF_MOVING|2||
|MAN_INT_OFF|3||
|MAN_INT_ON|4||
|MAN_LOW|5||
|MAN_HIGH|6||
|MAN_FLICK|7||
|WASH|8||
|AUTO_LOW|9||
|AUTO_HIGH|10||
|COURTESYWIPE|11||
|AUTO_ADJUST|12||
|STALLED|13||
|NO_DATA_EXISTS|14||

### LayoutMode

|Name|Value|Description|
|:---|:----|:----------|
|ICON_ONLY|0||
|ICON_WITH_SEARCH|1||
|LIST_ONLY|2||
|LIST_WITH_SEARCH|3||
|KEYBOARD|4||

### Language

|Name|Value|Description|
|:---|:----|:----------|
|EN-US|0||
|ES-MX|1||
|FR-CA|2||
|DE-DE|3||
|ES-ES|4||
|EN-GB|5||
|RU-RU|6||
|TR-TR|7||
|PL-PL|8||
|FR-FR|9||
|IT-IT|10||
|SV-SE|11||
|PT-PT|12||
|NL-NL|13||
|EN-AU|14||
|ZH-CN|15||
|ZH-TW|16||
|JA-JP|17||
|AR-SA|18||
|KO-KR|19||
|PT-BR|20||
|CS-CZ|21||
|DA-DK|22||
|NO-NO|23||

### FileType

|Name|Value|Description|
|:---|:----|:----------|
|GRAPHIC_BMP|0||
|GRAPHIC_JPEG|1||
|GRAPHIC_PNG|2||
|AUDIO_WAVE|3||
|AUDIO_MP3|4||
|AUDIO_AAC|5||
|BINARY|6||
|JSON|7||

### AudioType

|Name|Value|Description|
|:---|:----|:----------|
|PCM|0||

### TBTState

|Name|Value|Description|
|:---|:----|:----------|
|ROUTE_UPDATE_REQUEST|0||
|ROUTE_ACCEPTED|1||
|ROUTE_REFUSED|2||
|ROUTE_CANCELLED|3||
|ETA_REQUEST|4||
|NEXT_TURN_REQUEST|5||
|ROUTE_STATUS_REQUEST|6||
|ROUTE_SUMMARY_REQUEST|7||
|TRIP_STATUS_REQUEST|8||
|ROUTE_UPDATE_REQUEST_TIMEOUT|9||

### VehicleDataResultCode

|Name|Value|Description|
|:---|:----|:----------|
|SUCCESS|0||
|TRUNCATED_DATA|1||
|DISALLOWED|2||
|USER_DISALLOWED|3||
|INVALID_ID|4||
|VEHICLE_DATA_NOT_AVAILABLE|5||
|DATA_ALREADY_SUBSCRIBED|6||
|DATA_NOT_SUBSCRIBED|7||
|IGNORED|8||

### DisplayType

|Name|Value|Description|
|:---|:----|:----------|
|CID|0||
|TYPE2|1||
|TYPE5|2||
|NGN|3||
|GEN2_8_DMA|4||
|GEN2_6_DMA|5||
|MFD3|6||
|MFD4|7||
|MFD5|8||
|GEN3_8_INCH|9||

### ApplicationToNONEReason

|Name|Value|Description|
|:---|:----|:----------|
|DRIVER_DISTRACTION_VIOLATION|0||
|USER_EXIT|1||

### IgnitionStatus

|Name|Value|Description|
|:---|:----|:----------|
|UNKNOWN|0||
|OFF|1||
|ACCESSORY|2||
|RUN|3||
|START|4||
|INVALID|5||

### EmergencyEventType

|Name|Value|Description|
|:---|:----|:----------|
|NO_EVENT|0||
|FRONTAL|1||
|SIDE|2||
|REAR|3||
|ROLLOVER|4||
|NOT_SUPPORTED|5||
|FAULT|6||

### HMILevel

|Name|Value|Description|
|:---|:----|:----------|
|FULL|0||
|LIMITED|1||
|BACKGROUND|2||
|NONE|3||

### AppPriority

|Name|Value|Description|
|:---|:----|:----------|
|EMERGENCY|0||
|NAVIGATION|1||
|VOICE_COMMUNICATION|2||
|COMMUNICATION|3||
|NORMAL|4||
|NONE|5||

### PowerModeQualificationStatus

|Name|Value|Description|
|:---|:----|:----------|
|POWER_MODE_UNDEFINED|0||
|POWER_MODE_EVALUATION_IN_PROGRESS|1||
|NOT_DEFINED|2||
|POWER_MODE_OK|3||

### ApplicationsCloseReason

|Name|Value|Description|
|:---|:----|:----------|
|IGNITION_OFF|0||
|MASTER_RESET|1||
|FACTORY_DEFAULTS|2||
|SUSPEND|3||

### Dimension

|Name|Value|Description|
|:---|:----|:----------|
|NO_FIX|0||
|2D|1||
|3D|2||

### ImageType

|Name|Value|Description|
|:---|:----|:----------|
|STATIC|0||
|DYNAMIC|1||

### IgnitionStableStatus

|Name|Value|Description|
|:---|:----|:----------|
|IGNITION_SWITCH_NOT_STABLE|0||
|IGNITION_SWITCH_STABLE|1||
|MISSING_FROM_TRANSMITTER|2||

### WarningLightStatus

|Name|Value|Description|
|:---|:----|:----------|
|OFF|0||
|ON|1||
|FLASH|2||
|NOT_USED|3||

### VehicleDataNotificationStatus

|Name|Value|Description|
|:---|:----|:----------|
|NOT_SUPPORTED|0||
|NORMAL|1||
|ACTIVE|2||
|NOT_USED|3||

### SystemError

|Name|Value|Description|
|:---|:----|:----------|
|SYNC_REBOOTED|0||
|SYNC_OUT_OF_MEMMORY|1||

### PowerModeStatus

|Name|Value|Description|
|:---|:----|:----------|
|KEY_OUT|0||
|KEY_RECENTLY_OUT|1||
|KEY_APPROVED_0|2||
|POST_ACCESORY_0|3||
|ACCESORY_1|4||
|POST_IGNITION_1|5||
|IGNITION_ON_2|6||
|RUNNING_2|7||
|CRANK_3|8||

### ComponentVolumeStatus

|Name|Value|Description|
|:---|:----|:----------|
|UNKNOWN|0||
|NORMAL|1||
|LOW|2||
|FAULT|3||
|ALERT|4||
|NOT_SUPPORTED|5||

### PrimaryAudioSource

|Name|Value|Description|
|:---|:----|:----------|
|NO_SOURCE_SELECTED|0||
|USB|1||
|USB2|2||
|BLUETOOTH_STEREO_BTST|3||
|LINE_IN|4||
|IPOD|5||
|MOBILE_APP|6||

### RequestType

|Name|Value|Description|
|:---|:----|:----------|
|HTTP|0||
|FILE_RESUME|1||
|AUTH_REQUEST|2||
|AUTH_CHALLENGE|3||
|AUTH_ACK|4||
|PROPRIETARY|5||
|QUERY_APPS|6||
|LAUNCH_APP|7||
|LOCK_SCREEN_ICON_URL|8||
|TRAFFIC_MESSAGE_CHANNEL|9||
|DRIVER_PROFILE|10||
|VOICE_SEARCH|11||
|NAVIGATION|12||
|PHONE|13||
|CLIMATE|14||
|SETTINGS|15||
|VEHICLE_DIAGNOSTICS|16||
|EMERGENCY|17||
|MEDIA|18||
|FOTA|19||

### ConsentSource

|Name|Value|Description|
|:---|:----|:----------|
|GUI|0||
|VUI|1||

### CompassDirection

|Name|Value|Description|
|:---|:----|:----------|
|NORTH|0||
|NORTHWEST|1||
|WEST|2||
|SOUTHWEST|3||
|SOUTH|4||
|SOUTHEAST|5||
|EAST|6||
|NORTHEAST|7||

### BitsPerSample

|Name|Value|Description|
|:---|:----|:----------|
|8_BIT|0||
|16_BIT|1||

### EmergencyState

|Name|Value|Description|
|:---|:----|:----------|
|EMERGENCY_ON|0||
|EMERGENCY_OFF|1||

### Result

|Name|Value|Description|
|:---|:----|:----------|
|SUCCESS|0||
|UNSUPPORTED_REQUEST|1||
|UNSUPPORTED_RESOURCE|2||
|DISALLOWED|3||
|REJECTED|4||
|ABORTED|5||
|IGNORED|6||
|RETRY|7||
|IN_USE|8||
|DATA_NOT_AVAILABLE|9||
|TIMED_OUT|10||
|INVALID_DATA|11||
|CHAR_LIMIT_EXCEEDED|12||
|INVALID_ID|13||
|DUPLICATE_NAME|14||
|APPLICATION_NOT_REGISTERED|15||
|WRONG_LANGUAGE|16||
|OUT_OF_MEMORY|17||
|TOO_MANY_PENDING_REQUESTS|18||
|NO_APPS_REGISTERED|19||
|NO_DEVICES_CONNECTED|20||
|WARNINGS|21||
|GENERIC_ERROR|22||
|USER_DISALLOWED|23||
|TRUNCATED_DATA|24||

### CarModeStatus

|Name|Value|Description|
|:---|:----|:----------|
|NORMAL|0||
|FACTORY|1||
|TRANSPORT|2||
|CRASH|3||

### ImageFieldName

|Name|Value|Description|
|:---|:----|:----------|
|softButtonImage|0||
|choiceImage|1||
|choiceSecondaryImage|2||
|vrHelpItem|3||
|turnIcon|4||
|menuIcon|5||
|cmdIcon|6||
|appIcon|7||
|graphic|8||
|showConstantTBTIcon|9||
|showConstantTBTNextTurnIcon|10||
|locationImage|11||
|SubMenuIcon|12||

### VehicleDataType

|Name|Value|Description|
|:---|:----|:----------|
|VEHICLEDATA_GPS|0||
|VEHICLEDATA_SPEED|1||
|VEHICLEDATA_RPM|2||
|VEHICLEDATA_FUELLEVEL|3||
|VEHICLEDATA_FUELLEVEL_STATE|4||
|VEHICLEDATA_FUELCONSUMPTION|5||
|VEHICLEDATA_EXTERNTEMP|6||
|VEHICLEDATA_VIN|7||
|VEHICLEDATA_PRNDL|8||
|VEHICLEDATA_TIREPRESSURE|9||
|VEHICLEDATA_ODOMETER|10||
|VEHICLEDATA_BELTSTATUS|11||
|VEHICLEDATA_BODYINFO|12||
|VEHICLEDATA_DEVICESTATUS|13||
|VEHICLEDATA_ECALLINFO|14||
|VEHICLEDATA_AIRBAGSTATUS|15||
|VEHICLEDATA_EMERGENCYEVENT|16||
|VEHICLEDATA_CLUSTERMODESTATUS|17||
|VEHICLEDATA_MYKEY|18||
|VEHICLEDATA_BRAKING|19||
|VEHICLEDATA_WIPERSTATUS|20||
|VEHICLEDATA_HEADLAMPSTATUS|21||
|VEHICLEDATA_BATTVOLTAGE|22||
|VEHICLEDATA_ENGINETORQUE|23||
|VEHICLEDATA_ACCPEDAL|24||
|VEHICLEDATA_STEERINGWHEEL|25||

### UpdateResult

|Name|Value|Description|
|:---|:----|:----------|
|UP_TO_DATE|0||
|UPDATING|1||
|UPDATE_NEEDED|2||

### PRNDL

|Name|Value|Description|
|:---|:----|:----------|
|PARK|0||
|REVERSE|1||
|NEUTRAL|2||
|DRIVE|3||
|SPORT|4||
|LOWGEAR|5||
|FIRST|6||
|SECOND|7||
|THIRD|8||
|FOURTH|9||
|FIFTH|10||
|SIXTH|11||
|SEVENTH|12||
|EIGHTH|13||
|FAULT|14||

### VehicleDataStatus

|Name|Value|Description|
|:---|:----|:----------|
|NO_DATA_EXISTS|0||
|OFF|1||
|ON|2||

### EntityStatus
|Name|Value|Description|
|:---|:----|:----------|
|ON|0||
|OFF|1||

## The below describes the behavior related to RSDL functionality only.

### ModuleType

|    Param Name    |    Description                                  |
|------------------|-------------------------------------------------|
|    CLIMATE       |    Names the Climate module of the   vehicle    |
|    RADIO         |    Names the Radio module of the vehicle        |

### RadioBand

|  Param Name |    Description                       |
|-------------|--------------------------------------|
|    AM       |    AM (amplitude modulation) band    |
|    FM       |    FM (frequency modulation) band    |
|    XM       |    XM Satellite Radio                |

### RadioState

|  Param Name |  Description  |
|-------------|---------------|
|ACQUIRING|-|
|ACQUIRED|-|
|MULTICAST|-|
|NOT_FOUND|-|

### TemperatureUnit

|  Param Name |  Description  |
|-------------|---------------|
|KELVIN|-|
|FAHRENHEIT|-|
|CELSIUS|-|

### DefrostZone

|  Param Name |  Description  |
|-------------|---------------|
|FRONT|-|
|REAR|-|
|ALL|-|

### ButtonName

|    Param Name      |    Description                                            |
|--------------------|-----------------------------------------------------------|
|    AC_MAX          |    Max mode of Air Conditioning. Climate   button.        |
|    AC              |    Air   Conditioning. Climate button.                    |
|    RECIRCULATE     |    Recirculation mode.   Climate button.                  |
|    FAN_UP          |    Increment   the fan speed. Climate button.             |
|    FAN_DOWN        |    Decrement   the fan speed. Climate button.             |
|    TEMP_UP         |    Increment   the temperature. Climate button.           |
|    TEMP_DOWN       |    Decrement   the temperature. Climate button.           |
|    DEFROST_MAX     |    Max   mode of windshield defrost. Climate   button.    |
|    DEFROST         |    Windshield defrost.   Climate button.                  |
|    DEFROST_REAR    |    Rear   screen defrost. Climate button.                 |
|    UPPER_VENT      |    Upper   Vent System mode. Climate button.              |
|    LOWER_VENT      |    Lower   Vent System mode. Climate button.              |
|    VOLUME_UP       |    Increment   the volume. Radio button.                  |
|    VOLUME_DOWN     |    Decrement   the volume. Radio button.                  |
|    EJECT           |    Eject. Radio button.                                   |
|    SOURCE          |    Source. Radio button.                                  |
|    SHUFFLE         |    Shuffle. Radio button.                                 |
|    REPEAT          |    Repeat. Radio button.                                  |

### ButtonPressMode

|    Param Name    |    Description                                                                                                   |
|------------------|------------------------------------------------------------------------------------------------------------------|
|    LONG          |A button was released, after it was   pressed for a long time. Actual timing is defined by head unit and may vary |
|    SHORT         |A button was released, after it was   pressed for a short time. Actual timing is defined by head unit and may vary|

### DeviceRank

|   Param Name   |    Description                       |
|----------------|--------------------------------------|
|    DRIVER      |  The device is ranked as driver's    |
|    PASSEGER    |  The device is ranked as passenger's |