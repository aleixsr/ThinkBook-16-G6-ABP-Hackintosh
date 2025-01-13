# ThinkBook 16 G6 ABP Hackintosh
 OpenCore EFI for Lenovo ThinkBook 16 G6 ABP laptop

## Table of Contents

*   [Specifications](#specifications)
*   [What Works](#what-works)
*   [What Doesn't Work](#what-doesnt-work)
*   [Bios Options](#bios-options)
*   [Kexts Used](#kexts-used)
*   [SSDTs Used](#ssdts-used)
*   [Credits](#credits)
*   [Screenshots](#screenshots)

## Specifications
| **Component** | **Model** |
| ------------- | --------- |
| CPU | AMD Ryzen™ 7 7730U (8 cores, 16 threads) |
| RAM | 32GB (2 x 16GB) DDR4-3200 MHz (built-in) |
| IGPU | AMD Radeon™ (integrated)	|
| Display | 16" WUXGA (1920 x 1200), IPS, 45 % NTSC, 300 nits. *Use 1680x1050 as recommended resolution*. |
| NVMe | 1 TB SSD M.2 2242 PCIe Gen4 TLC |
| Audio | Realtek ACL257 |
| Wireless | Replaced by Intel AX200 |
| Ethernet | Realtek RTL8111 |

## What Works
| Item | Status | Notes |
| --- | --- | --- |
| CPU | ✅ | AMD Vanilla Kernel Patches ([Modify according to yours Core Count](https://github.com/AMD-OSX/AMD_Vanilla)) |
| iGPU | ✅⚠️ | **Some OpenGL issues** |
| Fn Keys | ✅ | SSDT & kext needed. |
| HDMI A/V out | ✅ | _Audio not tested_  |
| USB | ✅ | USB Toolbox + UTBMap|
| Keyboard | ✅ | Voodoops2controller Kext + Karabiner-Elements app for mapping |
| Audio | ✅⚠️ | AppleALC kext working with ***layout-id ???*** |
| Trackpad | ✅ | VoodooI2C |
| Intel WIFI | ✅ | AirportItlwm Kext |
| Bluetooth | ✅ | Internal Intel combo card with IntelBluetoothFirmware.kext + BlueToolFixup.kext.|
| Realtek Ethernet | ✅ | RealtekRTL8111 Kext|
| Battery | ✅ | VoodooBatteryStatus Kext |
| Shutdown/Reboot | ✅ | No issues reported |
| Sleep/Wake up | ⚠️| ***Work in Progress*** |

### OpenCore version: [1.0.2](https://github.com/acidanthera/opencorepkg/releases)

### Compatible macOS versions
 - Ventura (13.7)
 
## What Doesn't Work
| Item | Status | Notes |
| --- | --- | --- |
| Fingerprint Reader | ❌ | No kext |


<a href="https://www.buymeacoffee.com/aleixsr" target="_blank"><img src="https://cdn.buymeacoffee.com/buttons/v2/default-blue.png" alt="Buy Me A Coffee" style="height: 60px !important;width: 217px !important;" ></a>

***
> **You CAN NOT use SMBIOS from this repository, it MUST be unique for every macOS installation**

***

## BIOS Options
*   Turn off `Secure Boot` and `Fast Boot`
 
> **[!Warning]** Updating EFI may require clearing NVRAM to take full effect.

## Kexts Used

| Kext | Description |
| --- | --- |
| [Lilu.kext](https://github.com/acidanthera/Lilu) | Platform for arbitrary kext, library, and program patching throughout the system |
| [NootedRed.kext](https://github.com/ChefKissInc/NootedRed) | Lilu plugin for AMD Vega iGPUs |
| [AppleMCEReporterDisabler.kext](https://chefkissinc.github.io/Extras/Kexts/AppleMCEReporterDisabler.zip) | Disables AppleIntelMCEReporter which causes panics on AMD CPUs |
| [ForgedInvariant.kext](https://github.com/ChefKissInc/ForgedInvariant) | The Intel & AMD CPU TSC sync kext |
| [RestrictEvents.kext](https://github.com/acidanthera/RestrictEvents) | Blocking unwanted processes causing compatibility issues on different hardware and unlocking the support for certain features restricted to other hardware |
| [ECEnabler.kext](https://github.com/1Revenger1/ECEnabler) | Embedded Controller fields over 1 byte long needed for battery status |
| [BrightnessKeys.kext](https://github.com/acidanthera/BrightnessKeys) | Provides support for ACPI brightness change notifications from Fn keys |
| [AppleALC.kext](https://github.com/acidanthera/AppleALC) | Patches AppleHDA/AppleGFXHDA to allow unsupported audio codecs and HDMI audio |
| [NVMeFix.kext](https://github.com/acidanthera/NVMeFix) | Patches the NVMe stack (IONVMeFamily) to support Autonomous Power State Transition (APST), and to fix timeout kernel panics on some NVMe controllers |
| [USBToolBox.kext & UTBMap.kext](https://github.com/USBToolBox/kext) | USBToolBox kext is a kext intended to make common actions for USB mapping easier |
| [VirtualSMC.kext](https://github.com/acidanthera/VirtualSMC) | Advanced Apple SMC emulator in the kernel |
| [SMCProcessorAMD.kext](https://github.com/macos86/SMCProcessorAMD) | VirtualSMC plugin for AMD processors |
| [SMCBatteryManager.kext](https://github.com/acidanthera/VirtualSMC) | Enables battery readings |
| [SMCSuperIO.kext](https://github.com/acidanthera/VirtualSMC) | Monitors fan speeds |
| [SMCLightSensor.kext](https://github.com/acidanthera/VirtualSMC) | Adds support for ACPI Ambient Light Sensor |
| [SMCRadeonSensors.kext](https://github.com/ChefKissInc/RadeonSensor) | AMD GPU temperature monitoring on macOS |
| [VoodooPS2Controller.kext](https://github.com/acidanthera/VoodooPS2) | Fixes keyboard |
| [VoodooI2C.kext & VoodooI2CHID.kext](https://chefkissinc.github.io/Extras/Kexts/VoodooI2C.zip) | Driver for I2C input devices. The one linked is a pre-release version with added support for AMD I2C controllers|
| [RealtekRTL8111.kext](https://github.com/Mieze/RTL8111_driver_for_OS_X) | OS X open source driver for the Realtek RTL8111/8168 family |
| [AirportItlwm.kext](https://github.com/OpenIntelWireless) | Adds Intel WIFI support |
| [IntelBTPatcher.kext & IntelBluetoothFirmware.kext](https://github.com/OpenIntelWireless/IntelBluetoothFirmware) | Intel Bluetooth Kernel Extensions for macOS |
| [BlueToolFixup.kext](https://github.com/acidanthera/BrcmPatchRAM) | Patches Bluetooth stack to allow non-Apple Bluetooth |



## SSDTs Used

Done with [SSDTTime](https://github.com/corpnewt/SSDTTime) in Windows 11

| Table | Description |
| --- | --- |
| [SSDT-ALS0](https://chefkissinc.github.io/Extras/SSDTs/SSDT-ALS0.aml) | Adds a fake Ambient Light Sensor |
| [SSDT-EC](https://github.com/corpnewt/SSDTTime) | Adds a fake Embedded Controller device |
| [SSDT-PLUG-ALT](https://github.com/corpnewt/SSDTTime) | Fixes CPU definitions |
| [SSDT-PNLF](https://chefkissinc.github.io/Extras/SSDTs/SSDT-PNLF.aml) | Creates a fake PNLF device to allow for native brightness control on laptops |
| [SSDT-USBX](https://github.com/corpnewt/SSDTTime) | Enables USB Power Management |
| [SSDT-XOSI](https://github.com/corpnewt/SSDTTime) | Spoof macOS to Windows for some ACPI features |

## Credits
* [Noot AMD Hackintosh Guide](https://chefkissinc.github.io/guide)
* [The AMD Guide](https://the-amd-opencore-laptop-guide.gitbook.io/amd-laptops)
* [NootedRed Guide](https://chefkissinc.github.io/nred)
* [ChefKiss Telegram Group](https://t.me/+Bx3MO9Hq8whhNzk9)
* [AMD-OSX discord](https://discord.gg/EfCYAJW)
