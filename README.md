# Nitro5-2018_AN515-52_OpenCore
My macOS Sonoma OpenCore EFI files and some others. Change SMBIOS serials if you are re-using.<br>

## Specs:
| Component      | Description |
| ----------- | ----------- |
| Device      | Acer Nitro 5 (2018) AN515-53       |
| CPU   | Intel(R) Core(TM) i5-8300H CPU @ 2.30GHz        |
| Chipset | Intel HM370 (Coffee Lake) |
| RAM | DDR4 2666MHz 2x8GB |
| GPU | Nvidia GTX 1050 (Disabled in SSDT for lack of driver support in mac) |
| iGPU | Intel UHD Graphics 630 |
| Storage | SK hynix Gold P31 1TB PCIe NVMe Gen3 M.2 2280 SSD + 1TB Toshiba HDWL110 HDD |
| Display | 15.6" FHD (1920x1080) LCD |
| Trackpad | l2C HID Synaptics |
| Wireless | Intel Wireless-AC AC9560 160MHz w/ Bluetooth |
| Ethernet | Realtek |
| Audio | Realtek ALC225 (Layout 30) |
| OS | macOS Sonoma 14.7.6 + Windows 11 24H2 + Endeavour OS |
| OpenCore | v1.0.0 |

## What Works?
- All USB Ports including Type-C
- Intel UHD 630 iGPU w/Graphics Accelaration
- Display w/backlight control
- WiFi
- LAN
- Keyboard
- Keyboard Fn keys
- Trackpad
- Trackpad gestures
- m.2 and other SATA
- Audio (Speakers, Bluetooth Audio, 3.5mm port) + Mic
- Camera
- Battery capacity and indicator
- Device standby (Sleep) + Lid detection
- iMessage + Face time (w/Sonoma)
- USB Tethering
- Airdrop
- Screen Mirroring

## What's broken?
- Bluetooth
- Nvidia GTX1050 - Lack of driver support in mac
- HDMI - Connected to the dGPU

## Did not test
- SD card slot

## How to do it?

Just as the original Readme, I have no idea. I literally forked the efforts of [sameerasw](https://github.com/sameerasw) from his repo. The hardware of both variants of the AN515-53 and AN515-53 are quite similar, this helped with the compatibility of the EFI files. The first thing to do to make it boot was disable the SecureBootModel, or else it would have a Recovery Reboot. These changes would alllow me to boot Ventura.
To have Sonoma 14.4+ compatibility, first, updated the AirportItlwm.kext to the corresponding version for Sonoma 14.4+. Also replaced USBPorts.kex with USBToolBox.kext and UTBMap.kext (from Windows I generatedd the UTBMap).
Currently Bluetooth is broken. I don't use it that much so I may or may not fix it.
## Credits and ref
- [sameerasw's repo](https://github.com/sameerasw/Nitro5-2018_AN515-52_OpenCore)
- [Thread on tonymacx86.com](https://www.tonymacx86.com/threads/guide-oc-monterey-acer-nitro-5-an515-52-core-i7-8750h-samsung-1tb-960-evo-pcie-nvme.319629/)
- [Dortanis's guide](https://dortania.github.io/OpenCore-Install-Guide/)
- [pnapt's repo](https://github.com/pnapt/ACER-Nitro5-AN515-52-Opencore)
- [nerdynikhil's repo](https://github.com/nerdynikhil/Acer-Nitro-5-AN515-52-593F-OpenCore-Hackintosh)
- [duc010298-1's repo](https://github.com/duc010298-1/Acer-Nitro-5-AN515-52-Hackintosh-OC)
- [hanngoc1406's repo](https://github.com/hanngoc1406/Acer-Nitro-AN515-52-Hackintosh-OC-EFI)
- [acidanthera](https://github.com/acidanthera)
- [OpenCorePkg](https://github.com/acidanthera/OpenCorePkg)
- [r/hackintosh](https://www.reddit.com/r/hackintosh/)
- [To the members of my group](https://t.me/tidwib)

Enjoy! 
Keep hacking <3
