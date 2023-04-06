# Latitude-3310-OpenCore-EFI
OpenCore Bootloader Configuration for Dell Latitude 3310 to Boot macOS

## System Specification
| Platform |Dell Latitude 3310    |
|----------|----------------------|
| CPU      |Intel Core i3-8145U   |
| RAM      |4GB DDR4-2400         |
| iGPU     |UHD Graphics 620      |
| Ethernet |Realtek RTL8111       |
| WLAN/BT  |Intel Wireless-AC 9560|
| Storage  |Kioxia BG4 NVMe       |

## What's Working?
* PS/2 Keyboard
* PS/2 Trackpad (Partially)
* Native Power Management
* Integrated GPU
* Stereo Speaker
* Built-in Webcam, Mic
* WLAN, Bluetooth
* Sleep

## What's Broken?
* Trackpad Gesture/Multi-Touch
* AirDrop/Handoff/Sidecar (Intel Wireless)
* Brightness Keys
* Samsung PM991 NVMe SSD, SK Hynix SSD if you have one

## Enable Native Power Management Before First Boot
This disables the CFG Lock to allow MSR 0xE2 register to be written.  
Your BIOS firmware will be modified.  
* Press `SPACE` at OpenCore boot picker. Select `modGRUBShell.efi`.   
* At shell `grub>`, enter `setup_var 0x6ED 0x00`.  
* Reboot.

## Compatibility
* macOS Ventura (tested working)
* macOS Mojave - Monterey (untested, should work)
