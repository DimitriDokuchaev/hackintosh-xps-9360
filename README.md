# hackintosh-xps-9360
EFI configuration and assorted notes on the xps 9360 configuration

## The Laptop
 Dell XPS 13 9360
 
 Intel Core i5 7200U (Kaby Lake)
 
 Intel HD graphics 620
 
 8Gb LPDDR3 1866MHz Ram
 
 Toshiba 256NVME SSD (Replaced by a WD Blue 3D NAND 1TB M.2 SATA)
 
 Killer WiFi 1535 (Replaced by a BCM94360NG)
 
 BIOS version 2.15.1
 
 Webcam
 
## What does this use?
 This setup is based on the OpenCore bootloader.
 
## Why OpenCore vs. other solutions?
  OpenCore is the new standard for hackintosh building, compatibility is higher than ever even compared to the old and tried clover, setting OpenCore is easier then previous hackintosh bootloaders while making your computer behaving more like a mac.
  
## How was this achieved?
  I have followed [Dortanias guide](https://dortania-github-io.thrrip.space/OpenCore-Install-Guide/), the proof that building an hackintosh is easier than ever shows that a simple vanilla generic guide can be used to install macOS on almost any x86_64 hardware.
  
  During the build process debug version of the packages were used for troubleshooting purposes and then once everything was tested and working all packages were replaced by their release counterparts, this is all highlighted in Dortania's guide.
  
  When testing OpenCore with your config certain configurations are more approriate in order to be able to troubleshoot your issues, and once everything is working correctly you can apply the finishing touches, an example is the fact that i have included in my files opencanopy in the drivers folder, this is absolutely not needed to get macOS working, however i wanted to have a graphical boot similar to bootcamp when booting macOS so i decided to add it, obviously this means that the main configuration (config.plist) from when i was testing, experimenting and building my hackintosh is different to when i was just applying the finishing touches, which means that if you want to use my files you may need to adapt some of your configurations.
  Another example this config.plist is configured for filevault encryption, if your system does not have filevault enabled it will not work.
  
  I advise you if you are going to use some of my files to please understand what you are doing as there will be no support from my end, everything can be done/learnt from dortania's guide and a few /r/hackintosh posts.
  
  All SSDT patches were built manually based on the guide's instructions, you have all the required patches:
   - SSDT-PLUG - for cpu support and identification
   - SSDT-EC-USBX - for fixing support for embedded controllers
   - SSDT-PNLF - for backlight fixing
   - SSDT-GPIO - for trackpad and keyboard support
   - SSDT-AWAC - for system clock fixing
   - SSDT-YTBT and SSDT-TYPC - for USB C and thunderbolt support, it has issues, but its the best that could be done as when this hackintosh was built.
   - SSDT-GPRW - to prevent instant wake after sleeping
   - SSDT-BCKM - keyboard backlight control

 This set up was propper and up-to-date 9 months ago, however this hasn't been updated since then, this was also only tested on macOS Catalina, neither BigSur nor Montrrey were tested, feel free to test it, but expect things to break!
 This setup will eventually be updated for Monterey when I have time.

# Update 11-1-22

## MacOS Monterey 12.1

I have updated the files and configurations to support MacOS Monterey 12.1.

## What was done and updated?
- Open Core was updated to the latest version 0.75.
- HFSplus.efi updated to the latest version
- Open Core config.plist matches all the requirements to be compliant with version 0.75.
- Lilu updated to the latest version.
- Virtual smc and the all the other related kexts updated to latest version.
- WhateverGreen updated to the latest version.
- AppleALC updated to the latest version
- SataUnsuported.kext removed and replaced by CtlnaAHCIPort.kext due to a lot of sata controllers being dropped.

## Not updated (kept).
- voodoo packages are still the latest as the time of this writting, so not updated.
- ssdt patches kept as they are, still work on the latest version of MacOS Monterey.

## Enjoy, no support!
Again as mentioned above don't expect support on this setup, feel free to use the files and try stuff on your own. good luck!.
