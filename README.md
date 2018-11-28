# WIP (November 28, 2018)
# macOS for Acer Swift 3 SF314-52 
This project is to give the SF314-52 an almost complete and functional build of macOS 10.14.1 Mojave. I have been using it as my daily driver for a month and there are no major issues. Battery life is simmilar to Windows. My repo is based off of PavelIT's clover zip file for the 15" version of the Swift 3, I just changed a few things as some items were buggy.

## My Specs
BIOS: 1.07

CPU: Intel i5-8250U

GPU: Intel UHD 620

RAM: 8GB DDR4 

Display: FHD, 1920x1080

Storage: PCI-E NVME ADATA SX8200 240GB 

WiFi: Broadcom DW1560

## Note
Guide may be applicable to other Swift 3 models. Results may vary. If you need help, please ask.
If you use a USB wifi adapter don't expect sleep to work properly.
The original Intel 600p creates issues after sleep, converting drive to HFS+ after installation might fix the issue. Replacement drive is preferred.

If patching SSDT and DSDT, do the regular patches reccomended by Rehabman and the ones required by VoodooI2C for a functional and flawless touchpad experience.

# What Works
- Audio
- Keyboard / KB Backlight
- Battery
- USB Ports
- Trackpad with advanced features
- Brightness Control
- Sleep / Wake
- Webcam
- Bluetooth
- WiFi
- Keyboard Function Keys
- Keyboard Brightness Keys, needs Karabiner Elements

# What doesn't work
- Card Reader
- Touch ID

# Pre-Installation
1. Replace Intel SSD with anything that isn't Intel (unless converting to HFS+) and replace the WiFi adapter with a DW1560 (recomended) or use USB WiFi
2. Change your BIOS Settings: 
  - **Enable** Set Supervisor Password (1234)
  - **Disable** Secure Boot
  - **Enable** F12 Boot Menu 
  
# Installation
1. Create a macOS installation disk with a 16GB USB drive using RehabMan's guide
2. Restart laptop, hit F12 key and select the drive previously created
3. Wipe target disk and install

# Post-Installation
1. Install Clover
2. Drag all contents inside CLOVER folder to CLOVER folder on EFI partition (simple way)
3. Restart
4. Use KextBeast to atleast install CodecCommander.kext to /Library/Extensions or install all kexts from CLOVER folder to /Library/Extensions except for BrcmFirmwareData.kext
5. Patch your own DSDT and SSDT files or try using mine

## Credits
PavelIT, CanadianGreg (noob924)
