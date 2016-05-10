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
[TODO]

## Abbreviations and Definitions

Abbreviations used in this document are collected in the table below

| Abbreviation | Meaning     |
| :------------- | :------------- |
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
|VDOP|Vertical Dilution of Precision|
|VR|Voice Recognition|
|UTC|Universal Time Coordinate|
