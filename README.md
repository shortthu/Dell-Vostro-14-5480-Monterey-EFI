# Monterey OpenCore EFI folder for Dell Vostro 14-5480

*__Disclaimer:__ This repository is for documentation and storage purpose only. Don't use the same EFI folder for your machine even if it's the same model. This Readme will provide you the informations about what is included, and you should read this alongside with [Dortarina's OpenCore Install Guide](https://dortania.github.io/OpenCore-Install-Guide/) and [Dortarina's OpenCore Post-Install](https://dortania.github.io/OpenCore-Post-Install/) to understand more about what is used here.*

*__Disclaimer 2:__ This repository is for Monterey only.*

This is the EFI folder I've made for my (old) laptop to run Hackintosh based on this extremely helpful [guide](https://dortania.github.io/OpenCore-Install-Guide/) from Dortarina team.

The Hackintosh community is amazing.

If you've come to this repository and have any question or issue *about this repository only*, please feel free to open an issue. *Please don't ask me to troubleshoot your installation.*

## General information

### Laptop specs

Components | Name / Type
--- | ---
Model | Dell Vostro 14-5480
CPU | Intel Core i5-5200U
iGPU | Intel HD Graphics 5500
dGPU (unsupported in MacOS) | Nvidia Geforce 830M
RAM | 8GB DDR3L 1600Mhz (originally 4GB)
SATA SSD | 1TB Samsung 870 EVO (originally HDD)

### Other notable stuff

(These will help a lot in finding Kexts)

Components | Description
--- | ---
Keyboard & Touchpad | PS2 Connection
Audio codec | Realtek ALC3241 (ALC290)
Wi-Fi card | Intel Wireless-N 7265
Ethernet | Realtek Gigabit Ethernet (RTL8111)

### OpenCore version

Components | Version
--- | ---
OpenCorePkg | 8.0.3

### Not working

- Sleep (S3). It should be the Nvidia GPU that causes the problem but I have tried multiple ways to troubleshoot but no luck.

### Working

Pretty much everything else.

## Firmware Drivers

*Stored in [/EFI/OC/Drivers](/EFI/OC/Drivers)*

Must haves (to boot)

- HfsPlus.efi
- OpenRuntime.efi

Extra files:

- OpenCanopy.efi: beauty treatment.
- ResetNvramEntry.efi: adds an option to reset NVRAM on the OpenCore OS select screen (press <kbd>Space</kbd> to show).

## Kexts

*Stored in [/EFI/OC/Kexts](/EFI/OC/Kexts)*

### Must haves (to boot)

- Lilu.kext
- VirtualSMC.kext

### VirtualSMC Plugins

- SMCProcessor.kext
- SMCSuperIO.kext
- SMCBatteryManager.kext
- SMCDellSensors.kext (probably not needed)

### Graphics

- WhateverGreen.kext

### Audio

- AppleALC.kext

### Ethernet

- RealtekRTL8111.kext

### USB

__These kexts are for USB mapping on my own machine, please generate your own UTBMap.kext using [this guide](https://github.com/corpnewt/USBMap).__

- USBToolBox.kext
- UTBMap.kext

### Wi-Fi and Bluetooth

- BlueToolFixup.kext (Bluetooth)
- AirportItlwm.kext (Wi-Fi)

### Keyboard & Trackpad

- VoodooPS2Controller.kext

### Battery

- ECEnabler.kext (Without this the OS can't read battery status on my machine)

### Realtek Card Reader

- RealtekCardReader.kext
- RealtekCardReaderFriend.kext (To show it on System Information)

## SSDTs

*Stored in [/EFI/OC/ACPI](/EFI/OC/ACPI)*

TODO: Finish this section

## [config.plist](/EFI/OC/config.plist)

TODO: Finish this section
