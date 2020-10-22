## Overview

This document provides the information for integrating the SmartDeviceLink (SDL) Embedded Component (generally referred to as SDL Core) with vehicle Head Unit (HU)

SDL is a system that is installed on the HU and allows a connected application on the mobile device to utilize some vehicle functionality such as text-to-speech, voice recognition, display, hardware buttons, etc.

With SDL as the connectivity middleware in a vehicle's infotainment system, applications running on connected iOS and Android devices might be presented to the vehicle HMI.

This guideline describes:

   * The types of transports supported by SDL for communication with the HMI
   * How to connect over one of the supported transports
   * The types of messages and message formats used for communication
   * The API that needs to be supported by the vehicle HMI
   * Drawings showing exemplary display layouts for illustrating expected HMI behavior
   * Sequence Diagrams showing the sequence of messages to be sent and received between SDL and the HMI
   * Examples for each function call in different message formats corresponding to the transports currently supported

## How to use this guide

The SDL HMI Integration guidelines may seem daunting at first, but we're not asking you to read them from cover to cover at the start of your exploration into SDL. We recommend an implementation of SDL HMI as follows

  1. Get connected to SDL by following the [Getting Started](../getting-started) portion of these guidelines
  2. Once you're connected and registered, connect a sample app such as the [iOS RPC Builder](https://github.com/smartdevicelink/rpc_builder_app_ios) to start to understand the RPC messaging layer in SDL between core and your HMI.
  3. From there, you'll notice messages such as BasicCommunication.UpdateAppList. Use this guide to understand what those messages mean and how they can be leveraged in your HMI to provide the best possible user experience.

## Abbreviations and Definitions

Abbreviations used in this document are collected in the table below

| Abbreviation | Meaning     |
| :------------- | :------------- |
|ASC|App Service Consumer|
|ASP|App Service Provider|
|BT|Bluetooth|
|CID|Center Information Display|
|DID|Data Identifier|
|DTC|Diagnostic Trouble Code|
|ECU|Electronic Control Unit|
|GPS|Global Positioning System|
|GUI|Graphical User Interface|
|HDOP|Horizontal Dilution of Precision|
|HMI|Human Machine Interface|
|IVI|In Vehicle Infotainment|
|JSON|JavaScript Object Notation|
|PDOP|Positional Dilution of Position|
|RPC|Remote Procedure Call|
|SDE|Software Development Environment|
|SDL|SmartDeviceLink|
|SEE|Software Engineering Environment|
|TTS|Text To Speech|
|UTC|Universal Time Coordinate|
|VDOP|Vertical Dilution of Precision|
|VR|Voice Recognition|

## Previous versions of these docs

This documentation is transpiled from markdown in the [sdl_hmi_integrations GitHub repository](https://github.com/smartdevicelink/sdl_hmi_integration_guidelines/) to HTML. If you wish to view these guides as they were in the past you can navigate to [the releases page](https://github.com/smartdevicelink/sdl_hmi_integration_guidelines/releases) to view or download the markdown in a previous state.
