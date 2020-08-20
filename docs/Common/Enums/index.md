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
|USB_IOS|1||
|USB_AOA|2||
|WIFI|3||
|CLOUD_WEBSOCKET|4|Websocket connection used to connect to remote cloud application|

### EventTypes

|Name|Value|Description|
|:---|:----|:----------|
|PHONE_CALL|0|Phone call is active|
|EMERGENCY_EVENT|1|Active emergency event, active parking event|
|DEACTIVATE_HMI|2|GAL/DIO is active|
|AUDIO_SOURCE|3|Navigated to audio(radio, etc)|
|EMBEDDED_NAVI|4|Navigated to navigation screen|

### ButtonPressMode

|Name|Value|Description|
|:---|:----|:----------|
|LONG|0|A button was released, after it was pressed for a long time. Actual timing is defined by head unit and may vary|
|SHORT|1|A button was released, after it was pressed for a short time. Actual timing is defined by head unit and may vary|

### VRCommandType

|Name|Value|Description|
|:---|:----|:----------|
|Choice|0|Types that expound the current AddCommand should be processed as a choice for initiated PerformInteraction request for current active on HMI|
|Command|1|Types that expound the current AddCommand should be processed as a common command for current application on HMI|

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
|PROJECTION|10||
|REMOTE_CONTROL|11||

### CloudConnectionStatus

|Name|Value|Description|
|:---|:----|:----------|
|NOT_CONNECTED|0|No active websocket session or ongoing connection attempts|
|CONNECTED|1|Websocket is active|
|RETRY|2|Websocket connection failed and retry attempts are ongoing|

### WayPointType

|Name|Value|Description|
|:---|:----|:----------|
|ALL|0|All waypoints including destination|
|DESTINATION|1|Only destination|

### SpeechCapabilities

|Name|Value|Description|
|:---|:----|:----------|
|TEXT|0|Uses plain text for performing <abbr title="Text To Speech">TTS</abbr>|
|SAPI_PHONEMES|1|Uses the Speech API Phoneme representation of a phrase for performing <abbr title="Text To Speech">TTS</abbr>|
|LHPLUS_PHONEMES|2|Uses the LH+ Phoneme representation of a phrase for performing <abbr title="Text To Speech">TTS</abbr>|
|PRE_RECORDED|3||
|SILENCE|4||
|FILE|5|Uses an audio file sent to SDL via a PutFile RPC to perform <abbr title="Text To Speech">TTS</abbr> or play generic sounds in conjunction with <abbr title="Text To Speech">TTS</abbr>|

### TextFieldName

|Name|Value|Description|
|:---|:----|:----------|
|mainField1|0|The first line of first set of main fields of the persistent display *(applies to "Show")*|
|mainField2|1|The second line of first set of main fields of the persistent display *(applies to "Show")*|
|mainField3|2|The first line of second set of main fields of persistent display *(applies to "Show")*|
|mainField4|3|The second line of second set of main fields of the persistent display *(applies to "Show")*|
|statusBar|4|The status bar on NGN *(applies to "Show")*|
|mediaClock|5|Text value for MediaClock field *(applies to "Show")*|
|mediaTrack|6|The track field of NGN and GEN1.1 MFD displays. This field is only available for media applications *(applies to "Show")*|
|templateTitle|7|The title of the new template that will be displayed; applies to "Show"|
|alertText1|8|The first line of the alert text field *(applies to "Alert")*|
|alertText2|9|The second line of the alert text field *(applies to "Alert")*|
|alertText3|10|The third line of the alert text field *(applies to "Alert")*|
|scrollableMessageBody|11|Long form body of text that can include newlines and tabs *(applies to "ScrollableMessage")*|
|initialInteractionText|12|First line suggestion for a user response (in the case of <abbr title="Voice Recognition">VR</abbr> enabled interaction)|
|navigationText1|13|First line of navigation text|
|navigationText2|14|Second line of navigation text|
|ETA|15|Estimated Time of Arrival time for navigation|
|totalDistance|16|Total distance to destination for navigation|
|audioPassThruDisplayText1|17|First line of text for audio pass thru|
|audioPassThruDisplayText2|18|Second line of text for audio pass thru|
|sliderHeader|19|Header text for slider|
|sliderFooter|20|Footer text for slider|
|menuName|21|Primary text for Choice|
|secondaryText|22|Secondary text for Choice|
|tertiaryText|23|Tertiary text for Choice|
|menuTitle|24|Optional text to label an app menu button (for certain touchscreen platforms)|
|locationName|25|Optional name / title of intended location *(applies to SendLocation)*|
|locationDescription|26|Optional description of intended location / establishment *(applies to SendLocation)*|
|addressLines|27|Optional location address *(applies to SendLocation)*|
|phoneNumber|28|Optional phone number of intended location / establishment *(applies to SendLocation)*|
|timeToDestination|29||
|turnText|30||
|navigationText|31|Navigation text for UpdateTurnList|
|notificationText|32|Text of notification to be displayed on screen|

### MetadataType

|Name|Value|Description|
|:---|:----|:----------|
|mediaTitle|0|This field contains the title of the current audio track.|
|mediaArtist|1|This field contains the artist/creator of the current audio track.|
|mediaAlbum|2|This field contains the album title of the current audio track.|
|mediaYear|3|This field contains the creation year of the current audio track.|
|mediaGenre|4|This field contains the genre of the current audio track.|
|mediaStation|5|This field contains the name of the current media source.|
|rating|6|This field contains a rating of some form.|
|currentTemperature|7|This field contains the current temperature.|
|maximumTemperature|8|This field contains the maximum temperature for the day.|
|minimumTemperature|9|This field contains the minimum temperature for the day.|
|weatherTerm|10|This field contains the current weather (cloudy, clear, etc.).|
|humidity|11|This field contains the current humidity value.|

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
|NO_EVENT|0|The system does not have the adequate information to send valid YES or NO states|
|NO|1|The requested event is in NO state|
|YES|2|The requested event is in YES state|
|NOT_SUPPORTED|3|The requested data is not supported|
|FAULT|4|The module/sensor is currently faulty|

### KeyboardLayout

|Name|Value|Description|
|:---|:----|:----------|
|QWERTY|0||
|QWERTZ|1||
|AZERTY|2||

### MenuLayout

|Name|Value|Description|
|:---|:----|:----------|
|LIST|0||
|TILES|1||

### ButtonEventMode

|Name|Value|Description|
|:---|:----|:----------|
|BUTTONUP|0|A button has been released|
|BUTTONDOWN|1|A button has been pressed|

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
|MAIN|0|The app's persistent display (whether media/non-media/navigation) is fully visible onscreen <br> There is currently no user interaction (user-initiated or app-initiated) with the head-unit|
|VRSESSION|1|The system is currently in a <abbr title="Voice Recognition">VR</abbr> session (with whatever dedicated <abbr title="Voice Recognition">VR</abbr> screen being overlaid onscreen)|
|MENU|2| The system is currently displaying a system or in-App menu onscreen|
|HMI_OBSCURED|3|The app's display HMI is currently obscuring with either a system or other app's overlay (except of Alert element)|
|ALERT|4| Broadcast only to whichever app has an alert currently being displayed|

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
|ASCII|4|ASCII as defined in https://en.wikipedia.org/wiki/ASCII(codes 0-127).<br>Non-printable characters such as tabs and back spaces are ignored.|
|ISO_8859_1|5|Latin-1, as defined in https://en.wikipedia.org/wiki/ISO/IEC_8859-1|
|UTF_8|6|The UTF-8 character set that uses variable bytes per code point.<br>See https://en.wikipedia.org/wiki/UTF-8 for more details.<br>This is the preferred character set.|

### SamplingRate

|Name|Value|Description|
|:---|:----|:----------|
|8KHZ|0|Sampling rate of 8000 Hz|
|16KHZ|1|Sampling rate of 16000 Hz|
|22KHZ|2|Sampling rate of 22050 Hz|
|44KHZ|3|Sampling rate of 44100 Hz|

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
|CLOCK1|0|`minutesFieldWidth = 2`<br>`minutesFieldMax = 19`<br>`secondsFieldWidth = 2`<br>`secondsFieldMax = 99`<br>`maxHours = 19`<br>`maxMinutes = 59`<br>`maxSeconds = 59`<br>Is used for Type II, NGN and <abbr title="Center Information Display">CID</abbr> head units|
|CLOCK2|1|`minutesFieldWidth = 3`<br>`minutesFieldMax = 199`<br>`secondsFieldWidth = 2`<br>`secondsFieldMax = 99`<br>`maxHours = 59`<br>`maxMinutes = 59`<br>`maxSeconds = 59`<br>Is used for Type V head units|
|CLOCK3|2|`minutesFieldWidth = 2`<br>`minutesFieldMax = 59`<br>`secondsFieldWidth = 2`<br>`secondsFieldMax = 59`<br>`maxHours = 9`<br>`maxMinutes = 59`<br>`maxSeconds = 59`<br>Is used for GEN1.1 (i.e. MFD3/4/5) head units|
|CLOCKTEXT1|3|5 characters possible<br>`Format:      1|sp   c   :|sp   c   c`<br>`1|sp : digit "1" or space`<br>`c    : character out of following character set: sp|0-9|[letters]`<br>`:|sp : colon or space`<br>Is used for Type II head unit|
|CLOCKTEXT2|4|5 chars possible<br>`Format:      1|sp   c   :|sp   c   c`<br>`1|sp : digit "1" or space`<br>`c    : character out of following character set: sp|0-9|[letters]`<br>`:|sp : colon or space`<br>Is used for <abbr title="Center Information Display">CID</abbr> and NGN head unit|
|CLOCKTEXT3|5|6 chars possible<br>`Format:      1|sp   c   c   :|sp   c   c`<br>`1|sp : digit "1" or space`<br>`c    : character out of following character set: sp|0-9|[letters]`<br>`:|sp : colon or space`<br>Is used for Type V head unit|
|CLOCKTEXT4|6|6 chars possible <br>`Format:      c   :|sp   c   c   :   c   c`<br>`:|sp : colon or space`<br>`c    : character out of following character set: sp|0-9|[letters]`.<br>Is used for GEN1.1 (i.e. MFD3/4/5) head units|

### TouchType

|Name|Value|Description|
|:---|:----|:----------|
|BEGIN|0||
|MOVE|1||
|END|2||
|CANCEL|3||

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
|DEFAULT_ACTION|0| Default action occurs.  Standard behavior (e.g. SoftButton clears overlay)|
|STEAL_FOCUS|1|The calling app's dialog or related event should clear and the app should be brought into HMI_FULL|
|KEEP_CONTEXT|2|Current system context is maintained.  An overlay is persisted even though a SoftButton has been pressed and the notification sent|

### ButtonName

|Name|Value|Description|
|:---|:----|:----------|
|OK|0||
|PLAY_PAUSE|1||
|SEEKLEFT|2||
|SEEKRIGHT|3||
|TUNEUP|4||
|TUNEDOWN|5||
|PRESET_0|6||
|PRESET_1|7||
|PRESET_2|8||
|PRESET_3|9||
|PRESET_4|10||
|PRESET_5|11||
|PRESET_6|12||
|PRESET_7|13||
|PRESET_8|14||
|PRESET_9|15||
|CUSTOM_BUTTON|16||
|SEARCH|17||
|AC_MAX|18|CLIMATE Module|
|AC|19|CLIMATE Module|
|RECIRCULATE|20|CLIMATE Module|
|FAN_UP|21|CLIMATE Module|
|FAN_DOWN|22|CLIMATE Module|
|TEMP_UP|23|CLIMATE Module|
|TEMP_DOWN|24|CLIMATE Module|
|DEFROST_MAX|25|CLIMATE Module|
|DEFROST|26|CLIMATE Module|
|DEFROST_REAR|27|CLIMATE Module|
|UPPER_VENT|28|CLIMATE Module|
|LOWER_VENT|29|CLIMATE Module|
|VOLUME_UP|30|RADIO Module|
|VOLUME_DOWN|31|RADIO Module|
|EJECT|32|RADIO Module|
|SOURCE|33|RADIO Module|
|SHUFFLE|34|RADIO Module|
|REPEAT|35|RADIO Module|
|NAV_CENTER_LOCATION|36|Navigation Subscription Button|
|NAV_ZOOM_IN|37|Navigation Subscription Button|
|NAV_ZOOM_OUT|38|Navigation Subscription Button|
|NAV_PAN_UP|39|Navigation Subscription Button|
|NAV_PAN_UP_RIGHT|40|Navigation Subscription Button|
|NAV_PAN_RIGHT|41|Navigation Subscription Button|
|NAV_PAN_DOWN_RIGHT|42|Navigation Subscription Button|
|NAV_PAN_DOWN|43|Navigation Subscription Button|
|NAV_PAN_DOWN_LEFT|44|Navigation Subscription Button|
|NAV_PAN_LEFT|45|Navigation Subscription Button|
|NAV_PAN_UP_LEFT|46|Navigation Subscription Button|
|NAV_TILT_TOGGLE|47|Navigation Subscription Button|
|NAV_ROTATE_CLOCKWISE|48|Navigation Subscription Button|
|NAV_ROTATE_COUNTERCLOCKWISE|49|Navigation Subscription Button|
|NAV_HEADING_TOGGLE|50|Navigation Subscription Button|

### KeypressMode

|Name|Value|Description|
|:---|:----|:----------|
|SINGLE_KEYPRESS|0|Each keyPress is individually sent as the user presses the keyboard keys|
|QUEUE_KEYPRESSES|1|The keyPresses are queued and a string is eventually sent once the user chooses to submit their entry|
|RESEND_CURRENT_ENTRY|2|The keyPresses are queue and a string is sent each time the user presses a keyboard key; the string contains the entire current entry|

### WiperStatus

|Name|Value|Description|
|:---|:----|:----------|
|OFF|0|The wipers are off|
|AUTO_OFF|1|The wipers are automatically off|
|OFF_MOVING|2|Means that though set to off, somehow the wipers have been engaged (physically moved enough to engage a wiping motion)|
|MAN_INT_OFF|3|The wipers are manually off after having been working|
|MAN_INT_ON|4|The wipers are manually on|
|MAN_LOW|5|The wipers are manually set to low speed|
|MAN_HIGH|6|The wipers are manually set to high speed|
|MAN_FLICK|7|The wipers are manually set for doing a flick|
|WASH|8|The wipers are set to use the water from vehicle washer bottle for cleaning the windscreen|
|AUTO_LOW|9|The wipers are automatically set to low speed|
|AUTO_HIGH|10|The wipers are automatically set to high speed|
|COURTESYWIPE|11|This is for when a user has just initiated a WASH and several seconds later a secondary wipe is automatically initiated to clear remaining fluid|
|AUTO_ADJUST|12|This is set as the user moves between possible automatic wiper speeds|
|STALLED|13|The wiper is stalled to its place|
|NO_DATA_EXISTS|14|The sensor / module cannot provide any information for wiper|

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
|EN-US|0|English - US|
|ES-MX|1|Spanish - Mexico|
|FR-CA|2|French - Canada|
|DE-DE|3|German - Germany|
|ES-ES|4|Spanish - Spain|
|EN-GB|5|English - GB|
|RU-RU|6|Russian - Russia|
|TR-TR|7|Turkish - Turkey|
|PL-PL|8|Polish - Poland|
|FR-FR|9|French - France|
|IT-IT|10|Italian - Italy|
|SV-SE|11|Swedish - Sweden|
|PT-PT|12|Portuguese - Portugal|
|NL-NL|13|Dutch (Standard) - Netherlands|
|EN-AU|14|English - Australia|
|ZH-CN|15|Mandarin - China|
|ZH-TW|16|Mandarin - Taiwan|
|JA-JP|17|Japanese - Japan|
|AR-SA|18|Arabic - Saudi Arabia|
|KO-KR|19|Korean - South Korea|
|PT-BR|20|Portuguese - Brazil|
|CS-CZ|21|Czech - Czech Republic|
|DA-DK|22|Danish - Denmark|
|NO-NO|23|Norwegian - Norway|
|NL-BE|24|Dutch (Flemish) - Belgium|
|EL-GR|25|Greek - Greece|
|HU-HU|26|Hungarian - Hungary|
|FI-FI|27|Finnish - Finland|
|SK-SK|28|Slovak - Slovakia|
|EN-IN|29|English - India|
|TH-TH|30|Thai - Thailand|
|EN-SA|31|English - Middle East|
|HE-IL|32|Hebrew - Israel|
|RO-RO|33|Romanian - Romania|
|UK-UA|34|Ukrainian - Ukraine|
|ID-ID|35|Indonesian - Indonesia|
|VI-VN|36|Vietnamese - Vietnam|
|MS-MY|37|Malay - Malaysia|
|HI-IN|38|Hindi - India|

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
|PCM|0|Linear PCM|

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
|CID|0|A 2-line x 20 character "dot matrix" display|
|TYPE2|1|1 line older radio head unit|
|TYPE5|2|Old radio head unit|
|NGN|3|Next Generation Navigation display|
|GEN2_8_DMA|4|GEN-2, 8 inch display|
|GEN2_6_DMA|5|GEN-2, 6 inch display|
|MFD3|6|3 inch GEN1.1 display|
|MFD4|7|4 inch GEN1.1 display|
|MFD5|8| 5 inch GEN1.1 display|
|GEN3_8_INCH|9||
|SDL_GENERIC|10||

### ApplicationExitReason

|Name|Value|Description|
|:---|:----|:----------|
|DRIVER_DISTRACTION_VIOLATION|0|By getting this value, SDL puts the named app to NONE HMILevel|
|USER_EXIT|1|By getting this value, SDL puts the named app to NONE HMILevel|
|UNAUTHORIZED_TRANSPORT_REGISTRATION|2|By getting this value, SDL unregisters the named application|
|UNSUPPORTED_HMI_RESOURCE|3|By getting this value, SDL unregisters the named application|
|CLOSE_CLOUD_CONNECTION|4|By getting this value, SDL puts the named app to NONE HMILevel. Used by the HMI to close a cloud app connection|

### IgnitionStatus

|Name|Value|Description|
|:---|:----|:----------|
|UNKNOWN|0|The information is not acceptable|
|OFF|1|The ignition is off|
|ACCESSORY|2|The accessories are active (power windows, audio, display, etc.)|
|RUN|3|Ignition is active|
|START|4|Starter is switched|
|INVALID|5|The data is provided, but there is some sort of fault or problem|

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
|NO_FIX|0|No <abbr title="Global Positioning System">GPS</abbr> at all|
|2D|1|Longitude and lattitude|
|3D|2|Longitude and lattitude and altitude|

### ImageType

|Name|Value|Description|
|:---|:----|:----------|
|STATIC|0||
|DYNAMIC|1||

### AudioStreamingIndicator

|Name|Value|Description|
|:---|:----|:----------|
|PLAY_PAUSE|0|Default playback indicator.|
|PLAY|1|Indicates that a button press of the Play/Pause button would start the playback.|
|PAUSE|2|Indicates that a button press of the Play/Pause button would pause the current playback.|
|STOP|3|Indicates that a button press of the Play/Pause button would stop the current playback.|

### IgnitionStableStatus

|Name|Value|Description|
|:---|:----|:----------|
|IGNITION_SWITCH_NOT_STABLE|0||
|IGNITION_SWITCH_STABLE|1||
|MISSING_FROM_TRANSMITTER|2|Either the data is not accessible or the sensor is broken|

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
|UNKNOWN|0|The data is unknown|
|NORMAL|1|The volume is normal|
|LOW|2|The volume is low|
|FAULT|3|The module/sensor is currently faulted|
|ALERT|4|The component`s volume is in critical level|
|NOT_SUPPORTED|5|The data is not supported|

### PrimaryAudioSource

|Name|Value|Description|
|:---|:----|:----------|
|NO_SOURCE_SELECTED|0||
|CD|1||
|USB|2||
|USB2|3||
|BLUETOOTH_STEREO_BTST|4||
|LINE_IN|5||
|IPOD|6||
|MOBILE_APP|7||  
|AM|8||
|FM|9||
|XM|10||
|DAB|11||

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
|OEM_SPECIFIC|20||
|ICON_URL|21||

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
|8_BIT|0|Audio sample is 8 bits wide, unsigned|
|16_BIT|1| Audio sample is 16 bits wide, signed, and in little endian|

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
|UNSUPPORTED_RESOURCE|2|If this response is returned to core and the related HMI interface state is not available, core will return `success:false` to mobile. Otherwise core will return `success:true`|
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
|SAVED|25||
|READ_ONLY|26||

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
|softButtonImage|0|The image field for SoftButton|
|choiceImage|1|The first image field for Choice|
|choiceSecondaryImage|2|The secondary image field for Choice|
|vrHelpItem|3|The image field for vrHelpItem|
|turnIcon|4|The image field for Turn|
|menuIcon|5|The image field for the menu icon in SetGlobalProperties|
|cmdIcon|6|The image field for AddCommand|
|appIcon|7|The image field for the app icon (set by setAppIcon)|
|graphic|8|The primary image field for Show|
|secondaryGraphic|9|The secondary image field for Show|
|showConstantTBTIcon|10|The primary image field for ShowConstantTBT|
|showConstantTBTNextTurnIcon|11|The secondary image field for ShowConstantTBT|
|locationImage|12|The optional image of a destination / location|
|alertIcon|13|The image field for Alert|
|subMenuIcon|14|The image field for AddSubMenu.menuIcon|

### VehicleDataType

|Name|Value|Description|
|:---|:----|:----------|
|VEHICLEDATA_GPS|0|Notifies [GPSData](../structs/#gpsdata) may be subscribed|
|VEHICLEDATA_SPEED|1||
|VEHICLEDATA_RPM|2||
|VEHICLEDATA_FUELLEVEL|3||
|VEHICLEDATA_FUELLEVEL_STATE|4||
|VEHICLEDATA_FUELCONSUMPTION|5||
|VEHICLEDATA_EXTERNTEMP|6||
|VEHICLEDATA_VIN|7||
|VEHICLEDATA_GEARSTATUS|8||
|VEHICLEDATA_PRNDL|9||
|VEHICLEDATA_TIREPRESSURE|10||
|VEHICLEDATA_ODOMETER|11||
|VEHICLEDATA_BELTSTATUS|12||
|VEHICLEDATA_BODYINFO|13||
|VEHICLEDATA_DEVICESTATUS|14||
|VEHICLEDATA_ECALLINFO|15||
|VEHICLEDATA_AIRBAGSTATUS|16||
|VEHICLEDATA_EMERGENCYEVENT|17||
|VEHICLEDATA_CLUSTERMODESTATUS|18||
|VEHICLEDATA_MYKEY|19||
|VEHICLEDATA_BRAKING|20||
|VEHICLEDATA_WIPERSTATUS|21||
|VEHICLEDATA_HEADLAMPSTATUS|22||
|VEHICLEDATA_BATTVOLTAGE|23||
|VEHICLEDATA_ENGINETORQUE|24||
|VEHICLEDATA_ACCPEDAL|25||
|VEHICLEDATA_STEERINGWHEEL|26||
|VEHICLEDATA_TURNSIGNAL|27||
|VEHICLEDATA_FUELRANGE|28||
|VEHICLEDATA_ENGINEOILLIFE|29||
|VEHICLEDATA_ELECTRONICPARKBRAKESTATUS|30||
|VEHICLEDATA_CLOUDAPPVEHICLEID|31| Parameter used by cloud apps or the policy server to identify a head unit|
|VEHICLEDATA_OEM_CUSTOM_DATA|32||
|VEHICLEDATA_STABILITYCONTROLSSTATUS|33||
|VEHICLEDATA_WINDOWSTATUS|34||
|VEHICLEDATA_HANDSOFFSTEERING|35||

### VideoStreamingProtocol

|Name|Value|Description|
|:---|:----|:----------|
|RAW|0|Raw stream bytes|
|RTP|1|Real-time Transport Protocol|
|RTSP|2|Real-time Streaming Protocol|
|RTMP|3|Real-Time Messaging Protocol|
|WEBM|4|WebM container|

### VideoStreamingCodec

|Name|Value|Description|
|:---|:----|:----------|
|H264|0|MPEG-4 Advanced Video Coding|
|H265|1|High Efficiency Video Coding|
|Theora|2|Ogg Theora|
|VP8|3| VP8 can be multiplexed into the Matroska-based container format WebM along with Vorbis and Opus audio. The image format WebP is based on VP8's intra-frame coding|
|VP9|4|Similar to VP8, but VP9 is customized for video resolutions beyond high-definition video (UHD) and also enables lossless compression|

### UpdateResult

|Name|Value|Description|
|:---|:----|:----------|
|UP_TO_DATE|0||
|UPDATING|1||
|UPDATE_NEEDED|2||

### PRNDL

|Name|Value|Description|
|:---|:----|:----------|
|PARK|0|Parking|
|REVERSE|1|Reverse gear|
|NEUTRAL|2|No gear|
|DRIVE|3|Regular Drive mode|
|SPORT|4|Drive Sport mode|
|LOWGEAR|5|1st gear hold|
|FIRST|6||
|SECOND|7||
|THIRD|8||
|FOURTH|9||
|FIFTH|10||
|SIXTH|11||
|SEVENTH|12||
|EIGHTH|13||
|NINTH|14||
|TENTH|15||
|UNKNOWN|16||
|FAULT|17||

### TPMS

|Name|Value|Description|
|:---|:----|:----------|
|UNKNOWN|0|If set the status of the tire is not known.|
|SYSTEM_FAULT|1|TPMS does not function.|
|SENSOR_FAULT|2|The sensor of the tire does not function.|
|LOW|3|TPMS is reporting a low tire pressure for the tire.|
|SYSTEM_ACTIVE|4|TPMS is active and the tire pressure is monitored.|
|TRAIN|5|TPMS is reporting that the tire must be trained.|
|TRAINING_COMPLETE|6|TPMS reports the training for the tire is completed.|
|NOT_TRAINED|7|TPMS reports the tire is not trained.|

### VehicleDataStatus

|Name|Value|Description|
|:---|:----|:----------|
|NO_DATA_EXISTS|0||
|OFF|1||
|ON|2||

### ModuleType

|Name|Value|Description|
|:---|:----|:----------|
|CLIMATE|0||
|RADIO|1||
|SEAT|2||
|AUDIO|3||
|LIGHT|4||
|HMI_SETTINGS|5||

### RadioBand

|Name|Value|Description|
|:---|:----|:----------|
|AM|0||
|FM|1||
|XM|2||

### RadioState

|Name|Value|Description|
|:---|:----|:----------|
|ACQUIRING|0||
|ACQUIRED|1||
|MULTICAST|2||
|NOT_FOUND|3||

### TemperatureUnit

|Name|Value|Description|
|:---|:----|:----------|
|FAHRENHEIT|0||
|CELSIUS|1||

### DefrostZone

|Name|Value|Description|
|:---|:----|:----------|
|FRONT|0||
|REAR|1||
|ALL|2||
|NONE|3||

### VentilationMode

|Name|Value|Description|
|:---|:----|:----------|
|UPPER|0||
|LOWER|1||
|BOTH|2||
|NONE|3||

### RCAccessMode

|Name|Value|Description|
|:---|:----|:----------|
|AUTO_ALLOW|0|Any RC app can take immediately gain control a module when it is requested|
|AUTO_DENY|1|An RC app has control of a module until the app releases it, all requests for control of the module by other apps are rejected|
|ASK_DRIVER|2|The driver is prompted when an app requests control of a module that is currently being used|

### EntityStatus

|Name|Value|Description|
|:---|:----|:----------|
|ON|0||
|OFF|1||

### FuelType

|Name|Value|Description|
|:---|:----|:----------|  
|GASOLINE|0||  
|DIESEL|1||  
|CNG|2|For vehicles using compressed natural gas|  
|LPG|3|For vehicles using liquefied petroleum gas|
|HYDROGEN|4|For FCEV (fuel cell electric vehicle)|  
|BATTERY|5|For BEV (Battery Electric Vehicle), PHEV (Plug-in Hybrid Electric Vehicle), solar vehicles and other vehicles which run on a battery|

### TurnSignal

|Name|Value|Description|
|:---|:----|:----------|
|OFF|0|Turn signal is OFF|
|LEFT|1|Left turn signal is on|
|RIGHT|2|Right turn signal is on|
|BOTH|3|Both signals (left and right) are on|

### ElectronicParkBrakeStatus

|Name|Value|Description|
|:---|:----|:----------|
|CLOSED|0|Park brake actuators have been fully applied.|
|TRANSITION|1|Park brake actuators are transitioning to either Apply/Closed or Release/Open state.|
|OPEN|2|Park brake actuators are released.|
|DRIVE_ACTIVE|3|When driver pulls the Electronic Park Brake switch while driving "at speed".|
|FAULT|4|When system has a fault or is under maintenance.|

### LightName

|Name|Value|Description|
|:---|:----|:----------|
|FRONT_LEFT_HIGH_BEAM|0||
|FRONT_RIGHT_HIGH_BEAM|1||
|FRONT_LEFT_LOW_BEAM|2||
|FRONT_RIGHT_LOW_BEAM|3||
|FRONT_LEFT_PARKING_LIGHT|4||
|FRONT_RIGHT_PARKING_LIGHT|5||
|FRONT_LEFT_FOG_LIGHT|6||
|FRONT_RIGHT_FOG_LIGHT|7||
|FRONT_LEFT_DAYTIME_RUNNING_LIGHT|8||
|FRONT_RIGHT_DAYTIME_RUNNING_LIGHT|9||
|FRONT_LEFT_TURN_LIGHT|10||
|FRONT_RIGHT_TURN_LIGHT|11||
|REAR_LEFT_FOG_LIGHT|12||
|REAR_RIGHT_FOG_LIGHT|13||
|REAR_LEFT_TAIL_LIGHT|14||
|REAR_RIGHT_TAIL_LIGHT|15||
|REAR_LEFT_BRAKE_LIGHT|16||
|REAR_RIGHT_BRAKE_LIGHT|17||
|REAR_LEFT_TURN_LIGHT|18||
|REAR_RIGHT_TURN_LIGHT|19||
|REAR_REGISTRATION_PLATE_LIGHT|20|| 
|HIGH_BEAMS|501|Include all high beam lights: front_left and front_right|
|LOW_BEAMS|502|Include all low beam lights: front_left and front_right|
|FOG_LIGHTS|503|Include all fog lights: front_left, front_right, rear_left and rear_right|
|RUNNING_LIGHTS|504|Include all daytime running lights: front, left and right|
|PARKING_LIGHTS|505|Include all parking lights: front_left and front_right|
|BRAKE_LIGHTS|506|Include all brake lights: rear_left and rear_right|
|REAR_REVERSING_LIGHTS|507||
|SIDE_MARKER_LIGHTS|508||
|LEFT_TURN_LIGHTS|509|Include all left turn signal lights: front_left, rear_left, left_side and mirror_mounted|  
|RIGHT_TURN_LIGHTS|510|Include all right turn signal lights: front_right, rear_right, right_side and mirror_mounted|
|HAZARD_LIGHTS|511|Include all hazard lights: front_left, front_right, rear_left and rear_right|
|REAR_CARGO_LIGHTS|512| Cargo lamps illuminate the cargo area.|  
|REAR_TRUCK_BED_LIGHTS|513|Truck bed lamps light up the bed of the truck.|    
|REAR_TRAILER_LIGHTS|514|Trailer lights are lamps mounted on a trailer hitch.|  
|LEFT_SPOT_LIGHTS|515|It is the spotlights mounted on the left side of a vehicle.|  
|RIGHT_SPOT_LIGHTS|516|It is the spotlights mounted on the right side of a vehicle.|  
|LEFT_PUDDLE_LIGHTS|517|Puddle lamps illuminate the ground beside the door as the customer is opening or approaching the door.|  
|RIGHT_PUDDLE_LIGHTS|518| Puddle lamps illuminate the ground beside the door as the customer is opening or approaching the door.|
|AMBIENT_LIGHTS|801||
|OVERHEAD_LIGHTS|802||
|READING_LIGHTS|803||
|TRUNK_LIGHTS|804||
|EXTERIOR_FRONT_LIGHTS|901|Include exterior lights located in front of the vehicle. For example, fog lights and low beams|
|EXTERIOR_REAR_LIGHTS|902|Include exterior lights located at the back of the vehicle. For example, license plate lights, reverse lights, cargo lights, bed lights an trailer assist lights|
|EXTERIOR_LEFT_LIGHTS|903|Include exterior lights located at the left side of the vehicle. For example, left puddle lights and spot lights|
|EXTERIOR_RIGHT_LIGHTS|904|Include exterior lights located at the right side of the vehicle. For example, right puddle lights and spot lights|
|EXTERIOR_ALL_LIGHTS|905|Include all exterior lights around the vehicle|

### LightStatus

|Name|Value|Description|
|:---|:----|:----------|
|ON|0||
|OFF|1||  
|RAMP_UP|2||  
|RAMP_DOWN|3||  
|UNKNOWN|4||  
|INVALID|5||

### DisplayMode

|Name|Value|Description|
|:---|:----|:----------|
|DAY|0||
|NIGHT|1||
|AUTO|2||

### DistanceUnit

|Name|Value|Description|
|:---|:----|:----------|
|MILES|0||
|KILOMETERS|1||

### MassageZone

|Name|Value|Description|
|:---|:----|:----------|
|LUMBAR|0|The back of a multi-contour massage seat. or SEAT_BACK|
|SEAT_CUSHION|1|The bottom a multi-contour massage seat. or SEAT_BOTTOM|

### MassageMode

|Name|Value|Description|
|:---|:----|:----------|
|OFF|0||
|LOW|1||
|HIGH|2||

### MassageCushion

|Name|Value|Description|
|:---|:----|:----------|
|TOP_LUMBAR|0||
|MIDDLE_LUMBAR|1||
|BOTTOM_LUMBAR|2||
|BACK_BOLSTERS|3||
|SEAT_BOLSTERS|4||

### SeatMemoryActionType

|Name|Value|Description|
|:---|:----|:----------|
|SAVE|0|Save current seat positions and settings to seat memory.|
|RESTORE|1|Restore / apply the seat memory settings to the current seat.|
|NONE|2|No action to be performed.|

### SupportedSeat

|Name|Value|Description|
|:---|:----|:----------|
|DRIVER|0||
|FRONT_PASSENGER|1||

### DeliveryMode

|Name|Value|Description|
|:---|:----|:----------|
|PROMPT|0||
|DESTINATION|1||
|QUEUE|2||

### AppServiceType

|Name|Value|Description|
|:---|:----|:----------|
|MEDIA|0||
|WEATHER|1||
|NAVIGATION|2||

### ServiceUpdateReason

|Name|Value|Description|
|:---|:----|:----------|
|PUBLISHED|0|The service has just been published with the module and once activated to the primary service of its type, it will be ready for possible consumption|
|REMOVED|1|The service has just been unpublished with the module and is no longer accessible|
|ACTIVATED|2|The service is activated as the primary service of this type. All requests dealing with this service type will be handled by this service|
|DEACTIVATED|3|The service has been deactivated as the primary service of its type|
|MANIFEST_UPDATE|4|The service has updated its manifest. This could imply updated capabilities. **Note: Currently unimplemented**|

### SystemCapabilityType

|Name|Value|Description|
|:---|:----|:----------|
|NAVIGATION|0||
|PHONE_CALL|1||
|VIDEO_STREAMING|2||
|REMOTE_CONTROL|3||
|APP_SERVICES|4||
|DISPLAYS|5||
|SEAT_LOCATION|6||
|DRIVER_DISTRACTION|7|Describes capabilities when the driver is distracted|

### MediaType

|Name|Value|Description|
|:---|:----|:----------|
|MUSIC|0||
|PODCAST|1||
|AUDIOBOOK|2||
|OTHER|3||

### NavigationAction

|Name|Value|Description|
|:---|:----|:----------|
|TURN|0|Using this action plus a supplied direction can give the type of turn|
|EXIT|1||
|STAY|2||
|MERGE|3||
|FERRY|4||
|CAR_SHUTTLE_TRAIN|5||
|WAYPOINT|6||

### NavigationJunction

|Name|Value|Description|
|:---|:----|:----------|
|REGULAR|0|A junction that represents a standard intersection with a single road crossing another|
|BIFURCATION|1|A junction where the road splits off into two paths; a fork in the road|
|MULTI_CARRIAGEWAY|2|A junction that has multiple intersections and paths|
|ROUNDABOUT|3|A junction where traffic moves in a single direction around a central, non-traversable point to reach one of the connecting roads|
|TRAVERSABLE_ROUNDABOUT|4|Similar to a roundabout, however the center of the roundabout is fully traversable. Also known as a mini-roundabout|
|JUGHANDLE|5|A junction where lefts diverge to the right, then curve to the left, converting a left turn to a crossing maneuver|
|ALL_WAY_YIELD|6|Multiple way intersection that allows traffic to flow based on priority; most commonly right of way and first in, first out|
|TURN_AROUND|7|A junction designated for traffic turnarounds|

### Direction

|Name|Value|Description|
|:---|:----|:----------|
|LEFT|0||
|RIGHT|1||

### WindowType

|Name|Value|Description|
|:---|:----|:----------|
|MAIN|0|This window type describes the main window on a display|
|WIDGET|1|A widget is a small window that the app can create to provide information and soft buttons for quick app control|

### PredefinedWindows

|Name|Value|Description|
|:---|:----|:----------|
|DEFAULT_WINDOW|0|The default window is a main window pre-created on behalf of the app|
|PRIMARY_WIDGET|1|The primary widget of the app|

### ServiceType

|Name|Value|Description|
|:---|:----|:----------|
|VIDEO|0|Refers to the Video service.|
|AUDIO|1|Refers to the Audio service.|
|RPC|2|Refers to RPC service.|

### ServiceEvent

|Name|Value|Description|
|:---|:----|:----------|
|REQUEST_RECEIVED|0|When a request for a Service is received.|
|REQUEST_ACCEPTED|1|When a request for a Service is accepted.|
|REQUEST_REJECTED|2|When a request for a Service is rejected.|

### ServiceStatusUpdateReason

|Name|Value|Description|
|:---|:----|:----------|
|PTU_FAILED|0|When a Service is rejected because the system was unable to get a required Policy Table Update.|
|INVALID_CERT|1|When a Service is rejected because the security certificate is invalid/expired.|
|INVALID_TIME|2|When a Service is rejected because the system was unable to get a valid SystemTime from HMI, which is required for certificate authentication.|  
|PROTECTION_ENFORCED|3|When a Service is rejected because the system configuration ini file requires the service must be protected, but the app asks for an unprotected service.|
|PROTECTION_DISABLED|4|When a mobile app requests a protected service, but the system starts an unprotected service instead.|

### HybridAppPreference

|Name|Value|Description|
|:---|:----|:----------|
|MOBILE|0||
|CLOUD|1||
|BOTH|2||

### TransmissionType

|Name|Value|Description|
|:---|:----|:----------|
|MANUAL|0|Manual transmission.|
|AUTOMATIC|1|Automatic transmission.|
|SEMI_AUTOMATIC|2|Semi automatic transmission.|
|DUAL_CLUTCH|3|Dual clutch transmission.|
|CONTINUOUSLY_VARIABLE|4|Continuously variable transmission(CVT).|
|INFINITELY_VARIABLE|5|Infinitely variable transmission.|
|ELECTRIC_VARIABLE|6|Electric variable transmission.|
|DIRECT_DRIVE|7|Direct drive between engine and wheels.|
### CapacityUnit

|Name|Value|Description|
|:---|:----|:----------|
|LITERS|0||
|KILOWATTHOURS|1||
|KILOGRAMS|2||
