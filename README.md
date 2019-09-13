# MacOS on Thinkpad S1 Yoga 12
Hackintosh MacOS Mojave 10.14.6 and Catalina 10.15 Beta 7 on Thinkpad S1 Yoga 12 with hot patch

## Pre-Installation

### 1. Warning: check you BIOS version !!!

**You should update BIOS to version 1.20 at minimum !**

BIOS Summary of Changes at https://download.lenovo.com/pccbbs/mobiles/jeuj84ww.txt

<1.20>
- (New) Updated Fan table
- (Fix) Fixed an issue that Fan stops working even when temperature reaching trigger point.
...

<1.08>
- (New) Removed authentication of WLAN cards.

So if you want to be able to replace the Wifi card with a MacOS compatible card, Bios version 1.08 or above is mandatory.

--> Version 1.20 or later recommended.

### 2. BIOS settings

- Disable Computrace
- Disable Vtd / Vtx
- Enable CSM
- Enable USB3

### 3. Know your hardware

|Compenent|Reference|
|---|---|
|CPU|Intel Core i-5 5300U vPro|
|RAM|DDR3L 8GB Bus 1600MHz|
|GFX|Intel HD Graphics 5500|
|Sound|Intel HD Audio (Conexant CX22752 Audio Driver)|
|Display|12.5" FHD IPS LCD|
|WIFI|Intel Wireless N7265NGW -> I replaced Lenovo BCM94352Z|
|Touch panel|Synaptics Touch Digitizer V04 (USB Internal port)|
|Stylus digitizer|FHD 1920x1080 (12.5in)|
|Sensor Hub|ST Sensor Hub: gyroscope, Accelerometer, rotation detection, luminosity detection..|
|SD Card reader|Realtek RTS5227 PCI Express Card Reader|
|Camera|CON4B2E72 Integrated Camera (USB Internal port)|
|Extension Port|Onelink Dock port for extension module [Onelink Pro Dock](https://support.lenovo.com/us/en/solutions/pd029981)|


#### What will work:
- CPU
- HD Intel Graphic Card
- Power Management
- Sleep
- Camera
- Brightness
- Keyboard
- Trackpad and Trackpoint
- Sound
- USB ports, HDMI port, HDMI Audio-Out
- SD Card Reader

#### What will not work:
- Touchscreen
- ST Sensor Hub: gyroscope, Accelerometer, rotation detection, luminosity detection..

#### What will partially work:
- Tablet digitzer (with stylus): recognized as a mouse with button

#### WIFI :
Thinkpad Yoga 12 M.2 WIFI port is E keyed, so it's compatible with both A+E and E keys cards. So you can either use in it:

- Lenovo BCM94352Z (**FRU 04X6020**) which is M.2 **"E" keyed**.

## Installation

....

## Post-Installation

### 1. Tools needed

- Clover Installer (https://sourceforge.net/projects/cloverefiboot/)
- Clover Configurator (https://mackie100projects.altervista.org/download-clover-configurator/)
...

### 2. Kexts used
- VirtualSMC.kext (https://github.com/acidanthera/VirtualSMC)
- SMCProcessor.kext
- SMCBatteryManager.kext
- SMCSuperIO.kext
- Lilu.kext (https://github.com/acidanthera/Lilu)
- AppleALC.kext (https://github.com/acidanthera/AppleALC)
- CodecCommander.kext (https://bitbucket.org/RehabMan/os-x-eapd-codec-commander/downloads/)
- VoodooPS2Controller.kext (https://github.com/acidanthera/VoodooPS2)
- WhateverGreen.kext (https://github.com/acidanthera/WhateverGreen/releases)
- USBPorts.kext (on my EFI Folder)
- EFICheckDisabler.kext (on my EFI Folder)

## 3. Patched
- Copy S240.aml to /ACPI/patched/