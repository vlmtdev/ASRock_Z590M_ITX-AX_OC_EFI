# ASRock_Z590M_ITX-AX_i5-11600K_RX570 Hackintosh

EFI for ASROCK Z590M ITX/AX with OpenCore bootloader

### Specs:

| Component        | Brank                              |
| ---------------- | ---------------------------------- |
| CPU              | Intel Core i5 11600K               |
| GPU              | PowerColor RX 5500 XT 4GB          |
| Lan 2.5GBE       | Realtek 8125                       |
| Lan 1GBE         | Intel I219 V11                     |
| Audio            | Realtek ALC897                     |
| Ram              | 64GB DDR4 3200 MHz                 |
| Wireless.        | INTEL AX210                        |
| 1° NVMe SSD      | SPCC M.2 1TB                       |
| SmBios           | iMacPro1,1                         |
| BootLoader       | OpenCore 0.7.4                     |
| macOS            | 10.15.7, also tested 11.6 BigSur   |


### Works:

- [x] AMD RX 5500 XT HDMI/DP OUTPUT with audio, also PowerPlayTables injected to turn off ZeroRPM mode
- [x] ALC 897 AUDIO (Sound, Mic)
- [x] USB Ports, ports mapped (I don't use internal ports, you need to remap ports if necessary)
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

## Windows 10 dual-boot:
You need to install rEFInd with [this guide](https://github.com/dortania/Hackintosh-Mini-Guides/blob/master/refind.md), because booting Windows from Opencore is not good.
My refind.conf:
```
timeout 10

menuentry "Apple" {
    icon \EFI\refind\icons\os_mac.png
    volume 0E239BC6-F960-3107-89CF-1C97F78BB46B
    loader /EFI/OC/OpenCore.efi
}
menuentry "Shindows" {
    icon \EFI\refind\icons\os_win8.png
    volume 63A2FC5D-4F50-46ED-8DAD-B0AF52E2AEDC
    loader \EFI\Microsoft\Boot\bootmgfw.efi
}
menuentry "EFI Shell" {
    icon \EFI\refind\icons\tool_shell.png
    loader \EFI\tools\Shell_Full.efi
}

scanfor manual,external
```

## Credits

- [Apple](https://apple.com) for macOS;
- [Dortania](https://dortania.github.io/OpenCore-Install-Guide/config-laptop.plist/icelake.html) For great and detailed guides.
- [Hackintoshlifeit](https://github.com/Hackintoshlifeit) for Bios settings and part of readme;
- [Insanelymac](https://insanelymac.com) for files, experience and manuals.
