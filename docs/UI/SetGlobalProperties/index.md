## SetGlobalProperties

Type
: Function

Sender
: SDL

Purpose
: Set the UI properties of an application.

### Description

SDL requests to set-up the data for <abbr title="Voice Recognition">VR</abbr> help layout, the name and icon for in-application menu and the properties of the touchscreen keyboard.

The request may arrive for the application whether being active or in background on HMI (depends on Policy Table permissions applicable to mobile application request, by default allowed to operate in all HMI levels except of NONE).

The `vrHelp` parameter of the `SetGlobalProperties` RPC is used by the system to display the help items on the screen and the `helpPrompt` parameter is used by the system for playing out the associated <abbr title="Text To Speech">TTS</abbr> help prompt.

SDL sends SetGlobalProperties request with specific `<vrHelp>` and `<vrHelpTitle>` values to HMI in next cases:   

1.	If at any point in time, the application sends `SetGlobalProperties` RPC with the `vrHelp` **and** `helpPrompt` parameters, then SDL Core shall continue with the existing behavior of forwarding such requests to HMI and SDL Core shall delete its internal list and stop sending `SetGlobalProperties` RPC to HMI after each AddCommand/DeleteCommand request received from mobile.
2. If at any point in time, the application sends `SetGlobalProperties` RPC with **either** of `vrHelp` **or** `helpPrompt` parameters, then SDL Core shall continue with the existing behavior of forwarding such requests to HMI and SDL Core shall not delete its internal list and shall continue to update the parameter which was not provided by the application.  
3. In case mobile app sends `AddCommand` with `CommandType = Command`, SDL must send update values of `vrHelp` via `SetGlobalProperties` to HMI. _(Note: AddCommand requests related to choice set must NOT trigger the update of "vrHelp")_
4. In case mobile app sends _SetGlobalProperties_request_ to SDL:   
    - _SDL must_ omit the `autoCompleteText` parameter when forwarding to the HMI
        - if `autoCompleteText` is present and `autoCompleteList` is omitted, SDL will forward `autoCompleteList` with a single value, taken from `autoCompleteText`.
 
!!! NOTE

By default `vrHelpTitle` value is set to application name.

_**Notes for HMI expected behavior:**_

1. The system shall have the ability to receive and store multiple strings from `autoCompleteList` per app.   
2. When the system receives a new list of strings in `autoCompleteList` for a particular app, the system shall delete the previous list and replace it with the new list for that app.   
3. When any of the keyboard layouts are being used, the system shall reference the `autoCompleteList` strings for that app.   
4. As the user enters data on the keyboard, the system shall display values from `autoCompleteList` which match the entry.
5. The number of matching `autoCompleteList` strings displayed shall only be limited by the character length constraints of the HMI.
6. The system shall provide the user the ability to select one of the displayed matching `autoCompleteList` strings without having to enter the entire string.   
7. When the user selects one of the displayed matching `autoCompleteList` strings, the system shall submit that entry and not require further user input for submission.

!!!

### Request

#### Behavior

!!! MUST   

1. Store the information and associate it with appID.
    * Note: _Initially, the appID together with other application-related information is provided by SDL within UpdateAppList or OnAppRegistered RPCs._
2. Whenever the User activates <abbr title="Voice Recognition">VR</abbr>, set up the requested values for <abbr title="Voice Recognition">VR</abbr> help layout, the name and icon for in-application menu and the properties of the touchscreen keyboard (if supported):
    * display the list of commands available for voice recognition. SDL provides the title for this list (_vrHelpTitle_ parameter) and the list of commands itself (vrHelp parameter which is an array of VrHelpItem‘s).   
    * display the in-application menu for every active application on User’s request. It must contain SDL-requested commands (UI.AddCommand) and sub menus (UI.AddSubMenu). SDL provides the values for the name (_menuTitle_ parameter) and for the icon (menuIcon parameter) of this in-application menu. The values for in-application menu and touchscreen keyboard are allowed by SDL for navigation type of application only.   
    * display the onscreen keyboard upon User\`s request within the following condition: all keyboardProperties supported by HMI must be embodied in HMI_capabilities.json file. In this case SDL are able to compare keyboardProperties requested by mobile device with actual supported keyboardProperties and send to HMI only that are supported.    
    * use default keyboardProperties – parameter in case SDL transfers UI.SetGlobalProperties request with omitted or empty keyboardProperties param to HMI.   
    * _**Important Note:**_ _If HMI-defined <abbr title="Voice Recognition">VR</abbr> commands are accessible together with those provided by SDL via VR.AddCommand, HMI must:_ 
        * _add the corresponding <abbr title="Voice Recognition">VR</abbr> HMI-defined commands to the list of <abbr title="Voice Recognition">VR</abbr> help items provided by SDL via UI.SetGlobalProperties_
        * _display the complete list of available <abbr title="Voice Recognition">VR</abbr> commands (SDL-defined and HMI-defined ones) when the User activates <abbr title="Voice Recognition">VR</abbr>._
3. Respond to the request.   

!!!

#### Parameters

|Name|Type|Mandatory|Additional|
|:---|:---|:--------|:---------|
|vrHelpTitle|String|false|maxlength: 500|
|vrHelp|[Common.VrHelpItem](../../common/structs/#vrhelpitem)|false|array: true<br>minsize: 1<br>maxsize: 100|
|menuTitle|String|false|maxlength: 500|
|menuIcon|[Common.Image](../../common/structs/#image)|false||
|keyboardProperties|[Common.KeyboardProperties](../../common/structs/#keyboardproperties)|false||
|appID|Integer|true||
|menuLayout|[Common.MenuLayout](../../common/enums/#menulayout)|false||

### Response

|Result |Description |Message type WebSocket|Message type D-Bus|Message Params|
|:------|:-----------|:---------------------|:-----------------|:-------------|
|Success|SUCCESS: HMI has set the requested properties.|JSON response|Method return|code: 0|
|Failure|INVALID_ID:appID is not valid (e.g.does not exist)|JSON response|Method return|code: 13|
|Failure|INVALID_DATA: The data sent is invalid (invalid JSON syntax or parameters out of bounds or of wrong type)|JSON response|Method return|code: 11|
|Failure|GENERIC_ERROR: The unknown issue occurred or other codes are not applicable.|JSON response|Method return|code: 22|

!!! NOTE
In case HMI does not respond SDL's request during SDL-default timeout (10 sec), SDL will return GENERIC_ERROR  result code to the corresponding mobile app's request. Please see [Result Enumeration] for all SDL-supported codes.
!!!

[Result Enumeration]: ../../common/enums/#result

#### Parameters

This RPC has no additional parameter requirements

### Sequence Diagrams

|||
SetGlobalProperties for active app on HMI with <abbr title="Voice Recognition">VR</abbr> activation
![SetGlobalProperties](./assets/SetGlobalPropertiesActiveVRActivate.png)
|||

|||
SetGlobalProperties for active app with TTS.SetGlobalProperties_request, UI.SetGlobalProperties_request, VR.Started, VR.Stopped.   
![SetGlobalProperties](./assets/SetGlobalProperties_TTS_UI_VR.png)
|||

### JSON Message Examples

#### Example Request

```json
{
  "id" : 116,
  "jsonrpc" : "2.0",
  "method" : "UI.SetGlobalProperties",
  "params" :
  {
    "vrHelpTitle" : "Choose the action",
    "vrHelp" :
    [
        {
         "text" : "Pause",
         "image" :
          {
             "value" : "tmp/SDL/app/Pandora/icon_1067.jpg",
             "imageType" : "DYNAMIC"
          },
         "position" : 1
        },
        {
         "text" : "Resume",
         "image" :
          {
             "value" : "tmp/SDL/app/Pandora/icon_1083.jpeg",
             "imageType" : "DYNAMIC"
          },
         "position" : 2
        },
        {
         "text" : "Skip",
         "image" :
          {
             "value" : "tmp/SDL/app/Pandora/icon_1013.jpeg",
             "imageType" : "DYNAMIC"
          },
         "position" : 3
        },
        {
         "text" : "Bookmark",
         "image" :
          {
             "value" : "tmp/SDL/app/Pandora/icon_1046.jpeg",
             "imageType" : "DYNAMIC"
          },
         "position" : 4
        }
    ],
    "appID" : 53880
  }
}
```

#### Example Response

```json
{
  "id" : 116,
  "jsonrpc" : "2.0",
  "result" :
  {
    "code" : 0,
    "method" : "UI.SetGlobalProperties"
  }
}
```

#### Example Error

```json
{
  "id" : 116,
  "jsonrpc" : "2.0",
  "error" :
  {
    "code" : 11,
    "message" : "Invalid data",
    "data" :
    {
      "method" : "UI.SetGlobalProperties"
    }
  }
}
```
