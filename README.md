# WIP (November 28, 2018)
# macOS for Acer Swift 3 SF314-52 
This project is to give the SF314-52 an almost complete and functional build of macOS 10.14.1 Mojave. I use it as my daily driver and there are no major issues. Battery life is similar to Windows. My repo is based off of PavelIT's clover zip file for the 15" version of the Swift 3, I just changed a few things as some items were buggy.

## My Specs
BIOS: 1.07

CPU: 1.8 GHz Intel Core i5-8250U

GPU: Intel UHD Graphics 620 1536 MB

RAM: 8GB 2400 MHz DDR4 

Display: FHD, 1920x1080

Storage: PCI-E NVME ADATA SX8200NP 240GB + SATA Micron_1100_MTFDDAV256TBN

WiFi/BT: Broadcom DW1560

## Note
Guide may be applicable to other Swift 3 models. Results may vary. If you need help, please ask.
If you use a USB wifi adapter don't expect sleep to work properly.
The original Intel 600p creates issues after sleep, converting drive to HFS+ after installation might fix the issue. Replacement drive is preferred.

If patching SSDT and DSDT, do the regular patches recommended by RehabMan and the ones required by VoodooI2C for a functional and flawless touchpad experience.

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

# Bugs
- laptop randomly locks-up and restarts sometimes (usually under high load while using bluetooth)
- double tap to drag in accessibility doesn't work but triple finger drag works
- fans turn on too early

# Pre-Installation
1. Replace Intel SSD with anything that isn't Intel (unless converting to HFS+) and replace the WiFi adapter with a DW1560 (recommended) or use USB WiFi
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
4. Use KextBeast to install all kexts from :Library:Extensions folder to /Library/Extensions
5. Patch your own DSDT and SSDT files or try using mine

## Credits
PavelIT, CanadianGreg (noob924)
