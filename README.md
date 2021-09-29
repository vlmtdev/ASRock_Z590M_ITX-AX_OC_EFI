# ASRock_Z590M_ITX-AX_i5-11600K_RX570 Hackintosh

EFI for ASROCK Z590M ITX/AX with OpenCore bootloader

### Specs:

| Component        | Brank                              |
| ---------------- | ---------------------------------- |
| CPU              | Intel Core i5 11600K               |
| GPU              | AMD RX570 4GB                      |
| Lan 2.5GBE       | Realtek 8125                       |
| Lan 1GBE         | Intel I219 V11                     |
| Audio            | Realtek ALC897                     |
| Ram              | 64GB DDR4 3200 MHz                 |
| Wireless.        | INTEL AX210                        |
| 1° NVMe SSD      | SPCC M.2 1TB                       |
| SmBios           | iMac 20,1                          |
| BootLoader       | OpenCore 0.7.4                     |
| macOS            | 10.15.7, also tested 11.6 BigSur   |


### Works:

- [x] AMD RX570 HDMI/DP OUTPUT with audio 
- [x] ALC 897 AUDIO (Sound, Mic)
- [x] All USB Ports, ports mapped
- [x] Sleep, Wake, Speedstep
- [x] 1° CONTROLLER NVME PciE Gen4x4
- [x] 2° CONTROLLER NVME PciE Gen3x4
- [x] CONTROLLER SATA III
- [x] All Sensors (CPU, GPU, NVME, SATA, FANS)
- [x] Realtek RTL8125 LAN
- [x] Intel I219 V11 LAN
- [x] NVRAM

### Not working:
- [ ] INTEL AX210 Wireless (not supported by itwlm at this moment)

### MacOS bootable USB creation:
- Read the Dortania guide for creating your USB from Windows or macOS
- [Guide Dortania](https://dortania.github.io/OpenCore-Install-Guide/installer-guide/) - USB creation

## Bios settings
### Enable :
* SATA Operation : AHCI
* XHCI Hand-Off
* ABOVE 4G
* XMP 2.0 Profile 1 or AUTO
* Primary Graphics Adapter : PEG

### Disable : 
* Secure Boot
* Intel SGX
* Fastboot
* CFG LOCK
* Boot From Onboard LAN
* CSM
* IGPU Multi-Monitor

## Credits

- [Apple](https://apple.com) for macOS;
- [Dortania](https://dortania.github.io/OpenCore-Install-Guide/config-laptop.plist/icelake.html) For great and detailed guides.
- [Hackintoshlifeit](https://github.com/Hackintoshlifeit) for Bios settings and part of readme;
- [Insanelymac](https://insanelymac.com) for files, experience and manuals.
