# vera-cmdswitch
Vera plugin/implementation for creating devices that forward the "on" and "off" command to a command, i e a shell script

The device will pass 1 for "on" and 0 for "off" to the script as a commnand line parameter

## Overview
The plugin implements the following services:
* urn:upnp-org:serviceId:SwitchPower1
* urn:upnp-org:serviceId:Dimming1
* urn:upnp-org:serviceId:WindowCovering1

That makes it compatible with the following standard device files:
* D_BinaryLight1.xml
* D_DimmableLight1.xml
* D_WindowCovering1.xml

## Installation
Go to "Develop Apps" feature in your Vera. Choose "Luup files" and upload the I_CmdSwitch1.xml file

## Creating a device
You create a device by navigating to the "Devlop Apps" menu item in your Vera. There you choose "Create device" and fill in the following fields (Minimum):

1. Description - The name of your device
2. Upnp Device Filename - One of the three device files mentioned above, i e D_BinaryLight1.xml
3. Upnp Implementation Filename - I_CmdSwitch1.xml downloaded from this repository

Click "Create device" and then reload your Vera Luup Engine

## Configure your device
When the device shows up in your Vera you will find four new variables under advanced settings:
* OnCmd - This is the os command/shell script that will be run when the device it turned "on" (or "Up/Open" for WindowCovering)
* OffCmd - This is the os command/shell script that will be run when the device it turned "off" (or "Down/Closed" for WindowCovering)
