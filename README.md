# Ultimate Hacking Keyboard bootloader

This repository contains the bootloader of the [Ultimate Hacking Keyboard](https://ultimatehackingkeyboard.com/) based on [NXP Kinetis Bootloader](http://www.nxp.com/products/microcontrollers-and-processors/arm-processors/kinetis-cortex-m-mcus/kinetis-symbols-footprints-and-models/kinetis-bootloader:KBOOT) v2.0

The project actually being modified is in KBOOT\targets\MK22F51212\. 

To test the bootloader a binary properly configured has been added to the root folder of this repository. This binary is based on the UHK_Right Firmware project. 
To understand these modifications and apply them to the current version of the UHK Right firmware, follow the procedure in "Adapting UHK Project to KBOOT.docx" (Work in progress...)

******* FEATURES *******

This bootloader is a fully functional porting of KBOOT 2.0. It supports the full command set from KBOOT 2.0 and the device can be controlled and erased/programmed easily using
the blhost.exe tool provided by NXP and included in this repository. A GUI with a reduced set of features has also been created for Windows (KinetisFlashTool.exe).

Key features:

 - Communication through HID with any PC without the need of an additional driver.
 - Automatic timeout and jump to user application without any action from the user.
 - If no valid application is present, Bootloader will keep waiting for a communication through the HID USB port.
 - Every command sent to the BL includes a validation process inside the MCU to avoid any error in the communication.
 - The memory area of the BL is protected, so even if the update fails, user just needs to do a Power on Reset (Plug and Unplug the Keyboard) in order to launch the bootloader again.
 
 Features to be added:
 - Additional layer of security. Bootloader will not allow any kind of update until a PIN sequence has been introduced.
 
