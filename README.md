# HP-VICTUS-16-e0075AX Hackintosh

 <h2 align="center"> OpenCore EFI For HP Victus 16 Ryzen 5 5600H & NVIDIA GTX 1650</h2>
 OpenCore Ver: 1.0.1</br>
 MacOS Supported Ver: 
 
*   Sequoia

 ![About mac](https://github.com/user-attachments/assets/ad48aac0-ef6c-4cdd-ac9a-7c5914c0e6a5)

Check [Dortania's Guide](https://dortania.github.io/Anti-Hackintosh-Buyers-Guide/) for unsupported hardware like SSD and WLAN cards and replace them with supported ones<br/>
Use SSDT-Nvme-DISABLE.aml to disable the Nvme drives that are problematic, else disable it in config.plist 
## Table of Contents

*   [Specifications](#specifications)
*   [What's Working](#whats-working)
*   [What's not Working](#whats-not-working)
*   [Kexts Used](#kexts-used)
*   [Screenshots](#screenshots)

## Specifications
|                 | ‎ ‎ ‎ ‎ ‎ ‎ ‎ ‎ Laptop specifications‎ ‎ ‎ ‎ ‎ ‎ ‎ ‎ ‎ ‎ ‎ ‎ ‎ ‎ ‎ ‎ ‎ ‎ ‎ ‎ ‎ ‎ ‎ ‎ ‎ ‎ ‎ ‎ ‎ ‎ ‎ ‎ ‎ ‎ ‎ ‎ ‎ ‎ ‎ ‎ ‎              |
| ----------------------- | :------------------------------------------------------------------------- |   
| CPU                     | AMD Ryzen™ 5 5600H with Radeon Graphics                                    |
| iGPU                    | Radeon Graphics (Vega 8)                                                   |
| dGPU                    | NVIDIA GTX 1650 [DISABLED]                                     |
| Memory                  | 32GB DDR4 3200MHz                                                          |
| Storage                 | 512GB NVMe SK hynix SK hynix PC711 HFS512GDE9X073N   [UNSUPPORTED] |
||1TB NVMe WD Blue SN570 PCIe Gen4                                                          |
| Network                 | RTL8852AE 802.11ax PCIe Wireless Network Adapter [UNSUPPORTED]                         | 
|| RTL8111/8168/8411 PCI Express Gigabit Ethernet Controller|
| Audio|Realtek ALC245|
|LCD Panel| 16.1" FHD IPS 60Hz|

## What's Working

| Item | Status | Notes |
| --- | --- | --- |
| CPU | ✅ | AMD Vanilla Kernel Patches ([Modify according to yours Core Count](https://github.com/AMD-OSX/AMD_Vanilla)) |
| iGPU | ✅ | NootedRed |
| Brightness Control | ✅ | NootedRed |
| USB | ✅ | All ports working with [USBMap](https://github.com/corpnewt/USBMap "USBMap")|
| Keyboard | ✅ | Voodoops2controller.Kext |
| Mic | ✅ | Partially Working, Use the patch [AMDMicrophone](https://github.com/qhuyduong/AMDMicrophone) |
| Ethernet | ✅ | RealtekRTL8111.kext |
| Battery | ✅ | SMCBatteryManager.kext |
| iServices | ✅ | Message/Facetime tested and working |
| Shutdown/Reboot | ✅ | |
| Sleep/Wake | ✅ | |

## What's not Working

| Item | Status | Notes |
| --- | --- | --- |
| HDMI A/V out | ❌ | Connected to dGPU  |
| WIFI | ❌ | Unsupported Chipset |
| Bluetooth | ❌ | Unsupported Chipset |
| Audio | ❌ | AppleALC kext working with layout-id 11 |
| Trackpad | ❌ | Synaptics Touchpad with AMD I2C Controller |

## Kexts Used

| Kext | Description |
| --- | --- |
| [AMDRyzenCPUPowerManagement.kext](https://github.com/trulyspinach/SMCAMDProcessor) | Power management and monitoring of AMD processors |
| [AppleALC.kext](https://github.com/acidanthera/AppleALC) | Native macOS HD audio for not officially supported codecs |
| [AppleMCEReporterDisabler.kext](https://files.amd-osx.com/AppleMCEReporterDisabler.kext.zip) | Disables AppleIntelMCEReporter which causes panics on AMD CPUs |
| [AmdTscSync](https://github.com/naveenkrdy/AmdTscSync"AmdTscSync") | Synchronises the TimeStamp Counter (TSC). Generally only useful for AMD APUs (usually laptops) |
| [Lilu.kext](https://github.com/acidanthera/Lilu) | Platform for arbitrary kext, library, and program patching throughout the system |
| [NVMeFix.kext](https://github.com/acidanthera/NVMeFix) | Improve compatibility with non-Apple SSDs |
| [RealtekRTL8111.kext](https://github.com/Mieze/RTL8111_driver_for_OS_X) | Open source driver for the Realtek RTL8111/8168 family |
| [RestrictEvents.kext](https://github.com/acidanthera/RestrictEvents) | Blocking unwanted processes causing compatibility issues on different hardware and unlocking the support for certain features restricted to other hardware |
| [SMCAMDProcessor.kext](https://github.com/trulyspinach/SMCAMDProcessor) | Power management and monitoring of AMD processors |
| [SMCBatteryManager.kext](https://github.com/acidanthera/VirtualSMC) | Enables battery readings |
| [USBMap](https://github.com/corpnewt/USBMap "USBMap") | Python script for mapping USB ports in macOS and creating a custom injector kext |
| [VirtualSMC.kext](https://github.com/acidanthera/VirtualSMC) | Advanced Apple SMC emulator in the kernel |
| [VoodooPS2Controller.kext](https://github.com/acidanthera/VoodooPS2) | Fixes keyboard |
|[BrightnessKeys.kext](https://github.com/acidanthera/BrightnessKeys)|Provides support for ACPI brightness change notifications|
|[ECEnabler](https://github.com/1Revenger1/ECEnabler)|Allows macOS to read EC fields over 8 bits long, removing the need to split them manually. |
|[HoRNDIS.kext](https://github.com/jwise/HoRNDIS)|driver for Mac OS X that allows you to use your Android phone's native USB tethering mode to get Internet access.|
|[NootedRed.kext](https://github.com/ChefKissInc/NootedRed)|Lilu plugin for AMD Vega iGPUs.|
|[SMCRadeonSensors](https://github.com/ChefKissInc/SMCRadeonSensors)|AMD GPU temperature monitoring on macOS|
|[VoodooI2C.kext](https://chefkissinc.github.io/Extras/Kexts/VoodooI2C.zip)|Driver for I2C input devices.|
|[VoodooRMI.kext](https://github.com/VoodooSMBus/VoodooRMI)|Synaptic Trackpad driver over SMBus/I2C for macOS|

## Screenshots
![amd-power](https://github.com/user-attachments/assets/be0c0d78-3714-4728-84c0-f0112f86efac)
