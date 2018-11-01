# WIP (November 1, 2018)
# macOS for Acer Swift 3 SF314-52 
This project is to give the SF314-52 an almost complete and functional build of macOS 10.13 High Sierra

## My Specs 
Model: SF314-52

Bios: 1.07

CPU: Intel i5-8250U

GPU: Intel UHD 620

RAM: 8GB DDR4 

Display: FHD, 1920x1080

Storage: PCI-E NVME ADATA SX8200 240GB 

WiFi: Broadcom DW1560

## Note
Your laptop may or may not have the exact specs as mine. Results may vary. If you need help, please ask.
If you use a USB wifi adapter look for drivers from that model

# What Works
- Audio
- Keyboard / Backlight
- Battery
- USB Ports
- Trackpad
- Backlight
- Brightness
- Sleep / Wake
- Webcam
- Bluetooth
- WiFi

# What doesn't work

- Keyboard Brightness Keys
- Card Reader
- Touch ID

# Pre-Installation
1. Replace original wifi chipset with a DW1560 (Recommended) or use a USB wifi adapter (Not recommended)
2. You will have to wipe the entire disk 
3. Change your BIOS settings: 
  - **Enable** Set Supervisor Password (1234)
  - **Disable** Secure Boot
  - **Enable** F12 Boot Menu 
  
# Installation
1. Create a macOS installation disk with a 16GB or more USB
2. Install clover with UEFI only and drivers64UEFI - choose OsxAptioFix2Drv-64
3. Replace the original config.plist to the one I have provided
4. Place the kexts in CLOVER/kexts/other and the HFSPlus.efi in /CLOVER/drivers64UEFI
5. Boot into USB
6. Install macOS

# Post-Installation
1. Partition your disk to 2GB to install Clover 
2. Install Clover with these options: 
  - Install for UEFI booting only
  - Install Clover in the ESP
  - Themes - You can pick anything Theme you want.
  - Drivers64UEFI / EmuVariableUefi-64, FSInject-64, HFSPlus, and OsxAptioFix2Drv-64
  - Install all RC scripts on all other bootable OS X volume
  - Optional RC Scripts / disable sleep proxy client
  - (Optional) Pref panel
3. Replace the original config.plist with mine
4. Use KextWizard to install sata-100-unsupported, facksmc, and voodoops2
**Now** you should be able to boot without the USB
5. Reboot your computer and press F4 before proceeding into macOS
6. Now you will need to patch your DSDT and SSDT's. Follow this guide [here](https://www.tonymacx86.com/threads/guide-patching-laptop-dsdt-ssdts.152573/) Use MACiASL 6.1 to patch the DSDT and SSDT. 
7. Use the provided DSDT patches and SSDT patches. For Graphics_PNLF.txt in SSDT, **only** place in one of the SSDT 
8. Now place the newly patched DSDT and SSDT's into the CLOVER/ACPI/patched
9. Reboot and make sure everything works
10. Now use KextWizard to place the rest of the kexts that I provided into S/L/E 
11. Reboot once again to see if all are working. 
12. Now you have a almost completely working hackintosh!

## Credits
Ryan Wong, Gregory Ocol, PavelIT
