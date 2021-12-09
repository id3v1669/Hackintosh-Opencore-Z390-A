# Asus Z390-A Opencore Hackintosh


This is an OpenCore version of ASUS Z390-A Prime Hackintosh EFI. Used to tripleboot Mac OS, Windows and Linux(Ubuntu). It works on macOS Monterey 12.0.1(21A559). Sleep, Airdrop and Handoff are supported.

![image](OS_Screenshot.png)

## Notes
1. Mac boot chime is added. You may need to modify `config.plist/UEFI/Audio/AudioOut` and `config.plist/DeviceProperties/Add/PathToDevice` based you motherboard layout.
2. For USB ports I picked USBMap.kext without port limit patch. During postinstall probably you will need to make your own.


## Hardware
| Item | Brand | Model | Driver | Comment |
|-----|-----|-----|-----|-----|
| Motherboard | ASUS | Z390-A Prime | | |
| CPU | Intel | i9-9900K | | |
| RAM | XPG | XPG 2x16GB DDR4 3600 | | XMP 3600 |
| iGPU | Intel | UHD 630 | built-in | |
| dGPU | Saphire | RX5700 XT Nitro+ | built-in | |
| SSD1 | Samsung | 970 Evo Plus 2tb nvme | | Main SSD Mac OS |
| SSD2 | Samsung | 980 Pro 1tb nvme | | SSD Windows |
| SSD3 | Samsung | 870 QVO 1tb sata | | SSD Linux |
| Wireless | Broadcom | BCM94360cd PCI | built-in | |
| Ethernet | Intel | I219-V | [IntelMausi](https://github.com/acidanthera/IntelMausi) | |
| Audio | Realtek | ALC S1220A | [AppleALC](https://github.com/acidanthera/AppleALC) | Layout in DeviceProps |
| Monitor1 | Philips | 325E1 | | |
| Monitor2 | MSI | Optix AG32C | | |

*QCA61x4A is not supported. Follow [this guide](https://www.tonymacx86.com/threads/bcm94352z-installed-on-asus-z170i-pro-gaming-wifi-and-bt.191274) the replace the onboard wireless card. Theoretically BCM94352Z or BCM94360CS2 with adapter can work as well.

## BIOS Setup
| Name | Option |
| --- | --- |
| SW Guard Extensions (SGX) | Disabled |
| CFG Lock | Disabled |
| VT-d | Disabled |
| Above 4G Decoding | Enabled |
| Primary Display | PCIE |
| iGPU-Multi-Monitor | Enabled |
| DVMT Pre-Allocated | 128M |
| IOAPIC 24-119 Entries | Disabled |
| Network Stack | Disabled |
| Legacy USB Support| Enabled |
| Fast Boot | Disabled |
| OS Type | Other OS |
| Launch CSM | Disabled |

## Known issue
GPU fan spins at max RPM for several seconds during boot occasionally and runs normally in desktop. This is a XFX BIOS bug. The problem can be solved by flashing other similar RX 580 BIOS.

## Acknowledgement
Apple for macOS

acidanthera for OpenCore etc.

headkaze for Hackintool
