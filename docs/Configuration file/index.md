## SDL’s  configuration file structure (ini-file)
To configure some specific SDL rules or to define the filepathes and other SDL settings, smartDeviceLink.ini file is used. The file is divided into a sections, each section relates to the configuration of some functional area. Some of the settings have no reference to HMI behavior, anyway they are described for information purposes to understand particular properties. 
### HMI
|Parameter|Type|Example|Description|
|:---|:----|:----|:----------|
|ServerAddress|String|ServerAddress = 127.0.0.1|Address to connect HMI (web-socket only);See also WebSocket Transport| 
|ServerPort|Integer|ServerPort = 8087|ServerPort (web-socket only); See also WebSocket Transport|
|VideoStreamingPort|Integer|VideoStreamingPort = 5050|Port number for streaming video (in case of socket type); See also Configuring audio/video streaming parameters in smartDeviceLink.ini file|
|AudioStreamingPort|Integer|AudioStreamingPort = 5080|Port number for streaming audio (in case of socket type); See also Configuring audio/video streaming parameters in smartDeviceLink.ini file
|LaunchHMI|Boolean|LaunchHMI = false|Parameter defines whether SDL should wait for launching HMI; Open the $LinkToWebHMI in chromium browser|
|LinkToWebHMI|String|LinkToWebHMI = HMI//index.html|Link to index HMTL page|

### MAIN
|Parameter|Type|Example|Description|
|:---|:----|:----|:----------|
|SDLVersion|String|SDLVersion = {GIT_COMMIT}|SDL source version, represents as a git commit hash value|
|LogsEnabled|Boolean|LogsEnabled = true|SDL logging output enabled/disabled on system|
|AppConfigFolder|String|AppConfigFolder =|The path to application configuration folder where hmi_capabilities,smartDeviceLink.ini, log4cxx.properties are stored.Storage of Policy table files (preload, snapshot) is valid for OpenSource only. The default value is current working directory|
|AppStorageFolder|String|AppStorageFolder = /fs/rwdata/storage/sdl|The root folder for storing all applications folder|
|AppResourceFolder|String|AppResourceFolder =audio8bit.wav|Contains resourses. Default value is SDL working directory|
|ThreadStackSize|Integer|ThreadStackSize = 20480|ThreadStackSize used by SDL only if its required by sytem/platform, wisean empty value is defined or no such parameter exists, stack size will be PTHREAD`_`STACK_MIN(only SDL’s configurable value), which for<br>Ubuntu:<br>THREAD_STACK_MIN = 16384<br>QNX:<br>PTHREAD_STACK_MIN = 256
|MixingAudioSupported|Boolean|MixingAudioSupported = true|Defines if HMI support attenuated mode (able to mix audio sources)|
|HMICapabilities|String|HMICapabilities = hmi_capabilities.json|The filepath to the file of default HMICapabilities. In case HMI doesn’t send some capabilities to SDL, the values from the file are used by SDL|
|MaxCmdID|Int64|MaxCmdID = 2000000000|Maximum cmdId of VR command which may be registered on SDL|
|HMIHeartBeatTimeout|Integer|HMIHeartBeatTimeout = 3000|HMI's heartbeat timeout. The value specifies seconds to send  heartbeat to HMI from SDL|
|DefaultTimeout|Integer|DefaultTimeout = 20000|The response must be send to mobile application (SDL must respond after this timeout if HMI  haven’t respond to a request)|
|AppDirectoryQuota|Int64|AppDirectoryQuota = 104857600|Definines folder size in bytes limitation for any application on SDL|
|AppHMILevelNoneTimeScaleMaxRequests|Integer|AppHMILevelNoneTimeScaleMaxRequests = 0|Number of the requests allowed for the application in NONE HMI Level. If exceeded, the application will be unregistered|
|AppHMILevelNoneRequestsTimeScale|Integer|AppHMILevelNoneRequestsTimeScale = 10|Time period in which AppHMILevelNoneTimeScaleMaxRequests requests number allowed for the application in NONE HMI Level. If exceeded, the application will be unregistered|
|AppTimeScaleMaxRequests|Integer|AppTimeScaleMaxRequests = 0|Number of the requests allowed for the application in any HMI Level except of NONE. If exceeded, the application will be unregistered|
|AppRequestsTimeScale|Integer|AppRequestsTimeScale = 10|Time period in which AppTimeScaleMaxRequests  requests number allowed for the application in any HMI Level except of NONE. If exceeded, the application will be unregistered|
|PendingRequestsAmount|Integer|PendingRequestsAmount = 0|Number of the SDL pending requests allowed for an application. If exceeded, the application will be unregistered. If the value is “0”, the check will be skipped|
|HeartBeatTimeout|Integer|HeartBeatTimeout = 7000|Heart beat timeout used for protocol v3. Timeout must be specified in milliseconds. If timeout is 0 heart beat between Mobile device and SDL will be disabled|
|SupportedDiagModes|String Array=true|SupportedDiagModes = <br>0x01, 0x02, 0x03,<br>0x05, 0x06, 0x07,<br>0x09, 0x0A, 0x18,<br>0x19, 0x22, 0x3E|The list of diagnostic modes supported on a vehicle. Only only the stated values are allowed by SDL in terms of DiagnosticMessage RPC, others are rejected|
|SystemFilesPath|String|SystemFilesPath = /fs/images/ivsu`_`cache|The path to the system file directory for interoperation between SDL and System (e.g. IVSU files and others). If parameter is empty, SDL uses /tmp/fs/mp/images/ivsu_cache by default|
|UseLastState|Boolean|UseLastState = true|To restore the last TCP/IP transport state (name, applications or channels) on SDL on a new device connection and on disconnect|
|TimeTestingPort|Integer|TimeTestingPort = 8090|Port to obtain the performance information about   messages processing  on different component levels. Enabled if SDL built with TIME_TESTER flag|
|ReadDIDRequest|Integer,Array[2]=true|ReadDIDRequest = 5, 1|Limitation for a number of ReadDID requests (the 1st value) per seconds (the 2nd value)|
|GetVehicleDataRequest|Integer, Array[2]=true|GetVehicleDataRequest = 5, 1|Limitation for a number of GetVehicleData requests (the 1st value) per seconds (the 2nd value)|

### MEDIA MANAGER
|Parameter|Type|Example|Description|
|:---|:----|:----|:----------|
|StartStreamRetry|Integer, Array[2]=true|StartStreamRetry = 3, 1000|Where the 1st one of the values is a number of retries and the 2nd number is a timeout in seconds for request frequency|
|EnableRedecoding|Boolean|EnableRedecoding = false|If decoding on HMI is required?APTHR|
|VideoStreamConsumer|String|VideoStreamConsumer = socket|Pipe/file or socket type of data streaming|
|AudioStreamConsumer|String|AudioStreamConsumer = pipe|Pipe/file or socket type of data streaming
|NamedVideoPipePath|String|NamedVideoPipePath = video`_`stream`_`pipe|Named pipe will be defined as:<br>1.	`<fileName>` file in AppStorageFolder if the format of the parameter matchs the template: NamedVideoPipePath = `<fileName>`<br>2.	`<fileName>` file in `<path>` folder if the format of the parameter matchs the template: NamedVideoPipePath =`<path/fileName>`<br>3.	“video`_`stream`_`pipe” file in AppStorageFolder if NamedVideoPipePath has  an empty value<br>4.	“video`_`stream`_`pipe” file in AppStorageFolder if SDL has no permissions to write to `<path/fileName>` defined in NamedVideoPipePath|
|NamedAudioPipePath|String|NamedAudioPipePath = audio`_`stream`_`pipe|Named pipe will be defined as:<br>1.	`<fileName>` file in AppStorageFolder if the format of the parameter matchs the template: NamedAudioPipePath = `<fileName>`<br>2.	`<fileName>` file in `<path>` folder if the format of the parameter matchs the template: NamedAudioPipePath =`<path/fileName>`<br>3.	“audio`_`stream_pipe” file in AppStorageFolder if NamedAudioPipePath has  an empty value<br>4. “audio`_`stream_pipe” file in AppStorageFolder if SDL has no permissions to write to `<path/fileName>` defined in NamedAudioPipePath|
|VideoStreamFile|String|VideoStreamFile = video`_`stream`_`file|File path will be constructed using AppStorageFolder + VideoStreamFile|
|AudioStreamFile|String|AudioStreamFile = audio`_`stream`_`file|File path will be constructed using AppStorageFolder + name|
|RecordingFileSource|String|RecordingFileSource = audio.8bit.wav|The "RecordingFileSource" parameter defines the recording file source which used for emulation PerformAudioPassThru|	
|RecordingFileName|String|RecordingFileName = audio.wav|The "RecordingFileName" parameter defines the name and format of audio file for PerformAudioPassThru_request|	
|StopStreamingTimeout|Integer|StopStreamingTimeout = 1000|The timeout in milliseconds for mobile to stop streaming or end up session|
|AudioDataStoppedTimeout|Integer|AudioDataStoppedTimeout = 1000|Defines time in milliseconds for SDL to wait for the next package of raw data over audio service|
|VideoDataStoppedTimeout|Integer|VideoDataStoppedTimeout = 1000	|Defines time in milliseconds for SDL to wait for the next package of raw data over video service| 

### GLOBAL PROPERTIES
|Parameter|Type|Example|Description|
|:---|:----|:----|:----------|
|TTSDelimiter|Char|TTSDelimiter = ,|Defines the delimiter, which will be appended to each TTS chunck, e.g. helpPrompt/timeoutPrompt|
|HelpPrompt|String|HelpPrompt = Please speak one of the following commands,Please say a command|Default prompt items, separated by comma. The value is set up in case ResetGlobalProperties request from the application or SDL (in case of TTSGlobalPropertiesTimeout)|
|TimeoutPrompt|String|TimeoutPrompt = Please speak one of the following commands,<br>Please say a command|Default prompt to be spoken by VR-engine timeout (when system expects some action by user and the time for this action is going to be out)|
|HelpTitle|String|HelpTitle = Available Vr Commands List|Text to be set-up for default value of the title of help list
|TTSGlobalPropertiesTimeout|Integer|TTSGlobalPropertiesTimeout = 20|In case mobile app didn't send global properties request, then default global properties will be sent defined timeout in seconds<br>Max value<br>TTSGlobalPropertiesTimeout 64K

### FILESYSTEM RESTRICTIONS
|Parameter|Type|Example|Description|
|:---|:----|:----|:----------|
|PutFileRequest|Integer|PutFileRequest = 5|Max allowed number of PutFile requests for one application in NONE. The application will be unregistered in case the number of requests exceeded the limitation|
|DeleteFileRequest|Integer|DeleteFileRequest = 5|Max allowed number of DeleteFile requests for one application in NONE. The application will be unregistered in case the number of requests exceeded the limitation| 
|ListFilesRequest|Integer|ListFilesRequest = 5|Max allowed number of ListFiles requests for one application in NONE. The application will be unregistered in case the number of requests exceeded the limitation|

### VR COMMANDS
|Parameter|Type|Example|Description|
|:---|:----|:----|:----------|
|HelpCommand|String|HelpCommand = Help|Default command which initiates VR Help of the application|

###  AppInfo
|Parameter|Type|Example|Description|
|:---|:----|:----|:----------|
|AppInfoStorage|String|AppInfoStorage = app_info.dat|The path for applications information storage (for resumption purposes)|

### Security Manager
|Parameter|Type|Example|Description|
|:---|:----|:----|:----------|
|Protocol|String|Protocol = TLSv1.2, DTLSv1.0.|Supported protocol version TLSv1.2, DTLSv1.0.|
|KeyPath|String|KeyPath = client.key|Certificate and key path to pem file|
|CertificatePath|String|CertificatePath = client.crt|Certificate and key path to pem file|
|SSLMode|String|SSLMode = CLIENT|SSL mode could be SERVER or CLIENT|
|CipherList|String|CipherList = ALL|Could be “ALL” ciphers or a list of chosen|
|VerifyPeer|Boolean|VerifyPeer  = true|Defines if Mobile app certificate must be verified or not(could be used in both SSLMode Server and Client)|
|CACertificatePath|String|CACertificatePath = .|Preloaded CA certificates directory|
|ForceProtectedService|String|ForceProtectedService = Non|Force protected services (could be id's from 0x01 to 0xFF or “Non” value)|
|ForceUnprotectedService|String|ForceUnprotectedService = Non|Force unprotected services (could be id's from 0x01 to 0xFF or “Non” value)
|UpdateBeforeHours|Integer|UpdateBeforeHours = 24|The "UpdateBeforeHours" parameter defines the amount of time in hours for certificate expiration AND after expiration PTU sequence will be triggered|

### Policy
|Parameter|Type|Example|Description|
|:---|:----|:----|:----------|
|EnablePolicy|Boolean|EnablePolicy = true|Turn on/off policies|
|PreloadedPT|String|PreloadedPT = sdl`_`preloaded`_`pt.json|The filename of the preloaded policy table|
|PathToSnapshot|String|PathToSnapshot = sdl_snapshot.json|The filename of  the policy table snapshot|
|AttemptsToOpenPolicyDB|Integer|AttemptsToOpenPolicyDB = 5|Number of attempts to open policy DB|
|OpenAttemptTimeoutMs|Integer|OpenAttemptTimeoutMs = 500|Timeout between attempts during opening DB in milliseconds|

### TransportManager
|Parameter|Type|Example|Description|
|:---|:----|:----|:----------|
|TCPAdapterPort|Integer|TCPAdapterPort = 12345|Listening port form incoming mobile connection|

### ProtocolHandler
|Parameter|Type|Example|Description|
|:---|:----|:----|:----------|
|MaximumPayloadSize|Integer|MaximumPayloadSize = 1488|Packet with a payload bigger than # MaximumPayloadSize will be marked as a malformed. Parameter must be used for protocol v3 or higher.<br>1)In case of emty value,SDL uses the default value of 1488 bytes for validating MTU (maximum transferring unit) size.<br>2) If the value defined in MaximumPayloadSize parameter is less than 1488,the default value of 1488 bytes must be used by SDL.|
|FrequencyCount|Integer|FrequencyCount = 1000|Application shall send not more than<br>#FrequencyCount messages per #FrequencyTime mSecs<br>Frequency check could be disabled by setting #FrequencyTime or #FrequencyCount to “0”|
|FrequencyTime|Integer|FrequencyTime = 1000|The limitation in ms for sending number of the requests not more than #FrequencyCount|
|MalformedMessageFiltering|Integer|MalformedMessageFiltering = true|Enable filtering transport data stream;<br>On #MalformedMessageFiltering disabling, SDL will close the connection with the first malformed message detection|
|MalformedFrequencyCount|Integer|MalformedFrequencyCount = 10|Boundary value of malformed message detection for connection closure<br>Can be disabled by setting<br>#MalformedFrequencyTime or<br>#MalformedFrequencyCount to “0”
|MalformedFrequencyTime|Integer|MalformedFrequencyTime = 1000|Boundary value of malformed message detection for connection closure. In case the frequency of mailformed requests will be more than per#MalformedFrequencyTime, SDL will close the connection
|ExpectedConsecutiveFramesTimeout|Integer|ExpectedConsecutiveFramesTimeout = 10000|Timeout for waiting CONSECUTIVE frames of multiframe|


### ApplicationManager
|Parameter|Type|Example|Description|
|:---|:----|:----|:----------|
|ApplicationListUpdateTimeout|Integer|ApplicationListUpdateTimeout = 2000|Application list update timeout ms|
|ThreadPoolSize|Integer|ThreadPoolSize = 1|Max allowed threads for handling mobile requests. Currently max allowed is 2|
|HashStringSize|Integer|HashStringSize = 32|The max size of hash which is used by OnHashUpdated()|

### SDL4
|Parameter|Type|Example|Description|
|:---|:----|:----|:----------|
|EnableProtocol4|Boolean|EnableProtocol4 = true|Enables SDL 4.0 support. Parameter allows to switch SDL4 functionality on SDL|
|AppIconsFolder|String|AppIconsFolder = storage|The path where apps’ icons must be stored. Upon each start SDL  must check whether the folder ‘AppIconsFolder’ exists and read/write permissions.<br>In case folder doesn’t exist, SDL creates it and uses it as assigned|
|AppIconsFolderMaxSize|Integer|AppIconsFolderMaxSize = 104857600|Max size of the folder in bytes. Parameter defines the allowed size in bytes of the folder for SDL to store the applications icons.|
|AppIconsAmountToRemove|Integer|AppIconsAmountToRemove = 1|Amount of the oldest icons to remove from "AppIconsFolder" in case of max folder size was reached.<br>In case the value ‘AppIconsAmountToRemove’ is equal zero SDL internally logs error and  continues working without storing the icon.| 

### Resumption
|Parameter|Type|Example|Description|
|:---|:----|:----|:----------|
|ApplicationResumingTimeout|Integer|ApplicationResumingTimeout = 3000|# Timeout in milliseconds for resumption Application HMILevel and resolving conflicts in case if multiple applications initiate resumption|
|AppSavePersistentDataTimeout|Integer|AppSavePersistentDataTimeout = 10000|Timeout in milliseconds for pereodical saving resumption persisten data|
|ResumptionDelayBeforeIgn|Integer|ResumptionDelayBeforeIgn = 30|Timeout in seconds to store hmi`_`level for media app before ign_off|
|ResumptionDelayAfterIgn|Integer|ResumptionDelayAfterIgn = 30|Timeout in seconds to restore hmi_level for media app after sdl run|
|UseDBForResumption|Boolean|UseDBForResumption = false|Resumption ctrl uses JSON if UseDBForResumption=false for store data otherwise uses DB|
|AttemptsToOpenResumptionDB|Integer|AttemptsToOpenResumptionDB = 10|Number of attempts to open resumption DB|
|OpenAttemptTimeoutMsResumptionDB|Integer|OpenAttemptTimeoutMsResumptionDB = 1000|Timeout between attempts during opening DB in milliseconds|

### AppLaunch
|Parameter|Type|Example|Description|
|:---|:----|:----|:----------|
|AppLaunchWaitTime|Integer|AppLaunchWaitTime = 5000|Time in milliseconds started from device connection - after expiring SDL remotely launches all known not-yet-registered apps from this device|
|AppLaunchMaxRetryAttempt|Integer|AppLaunchMaxRetryAttempt = 3|The number of times SDL attempts to launch an application after device connection - applied separately to each application from the given device|
|AppLaunchRetryWaitTime|Integer|AppLaunchRetryWaitTime = 15000|Time in milliseconds started by SDL after app launch request. if expired and app did not register, SDL sends new launch request. applied separately|
|RemoveBundleIDattempts|Integer|RemoveBundleIDattempts = 3|The number of the given device connections that the requested application failed to register after SDL's launch attempts - SDL removes app's bundleID|
|MaxNumberOfiOSDevice|Integer|MaxNumberOfiOSDevice = 10|The maximum number of iOS devices for which entries can be remembered by SDL|
|WaitTimeBetweenApps|Integer|WaitTimeBetweenApps = 4000|Time in milliseconds started after request to launch the first app. after either expires or the first app registers SDL requests to launch|
|EnableAppLaunchIOS|Boolean|EnableAppLaunchIOS = true|App Launch on iOS devices SDL feature enabler/disabler
