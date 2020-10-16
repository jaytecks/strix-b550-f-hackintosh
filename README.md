# STRIX B550-F GAMING Hackintosh
My EFI files for my desktop hack. Motherboard is an ASUS Strix B550-F GAMING

[Help downloading or using this EFI](https://github.com/ThatsNiceGuy/strix-b550-f-hackintosh/blob/master/README.md#installation-and-usage)
## What works
- Full support for Catalina 10.15 with OpenCore 0.5.9
- Audio
- Ethernet
  - Some issues have been found; if your Hackintosh kernel panics when you try to boot then disable Ethernet in the BIOS. Alternatively, you can remove the `device-id` key under `PciRoot(0x0)/Pci(0x1,0x2)/Pci(0x0,0x2)/Pci(0x9,0x0)/Pci(0x0,0x0)` in the DeviceProperties section
- USB (probably, haven't tested all ports)
- Wi-Fi if you have a wireless card
- Bluetooth if you have a wireless card
- All iCloud and Continuity features if you have a macOS supported wireless card

## Known issues
- Sidecar doesn't work - [See here](https://github.com/AMD-OSX/bugtracker/issues/1)
- Apple Watch simulator in Xcode doesn't work (normal for AMD hacks apparently)

## To-do list

**High priority**
- [x] Get macOS Catalina booting successfully
- [x] Get system perfectly running Catalina (WiFi, audio, etc)
  - **Not pushed to github yet!**

**Medium priority**

no medium priority stuff yet

**Low priority**
- [x] Get macOS Big Sur booting successfully
  - **Only Beta 4 and earlier work! fixing soon**
  
# Installation and Usage

## Requirements
- Ability to use a plist editor
- Ability to read instructions
- Good knowledge of navigating filesystems


**Table of contents**
- [Step 1 - Intended system config](https://github.com/ThatsNiceGuy/strix-b550-f-hackintosh/blob/master/README.md#step-1---intended-system-config)
- [Step 2 - Recommended BIOS settings](https://github.com/ThatsNiceGuy/strix-b550-f-hackintosh/blob/master/README.md#step-2---recommended-bios-settings)
- [Step 3 - iCloud setup]()
- [Step 4 - Downloading the EFI]()
- [Step 5 - Transferring to your storage device]()

## Step 1 - Intended system config
**What hardware is best supported and how**
- An ASUS Strix B550-F GAMING motherboard
- Ryzen 3000 series processor 
  - Ryzen 3 2200G and Ryzen 5 2400G are **not supported**
  - I used a Ryzen 5 3600
- Graphics card in first PCIe x16 slot
  - I used a reference Vega 56 from Gigabyte
- Wireless card in second PCIe x16 slot
  - An Apple AirPort card is your best bet. I used an AirPort BCM943602CS card in an adapter
- NVMe SSD inside the top M.2 slot
  - Leaving the slot empty is fine
- SATA SSD Inside the bottom M.2 slot
  - Leaving the slot empty is fine
  - Try not to put an NVMe SSD in this slot, as it will reduce the amount of PCIe lanes available to your GPU

**You must follow the pcie slot placements to use this EFI as-is. If you would like to put things in different slots, you'll have to configure DeviceProperties yourself.**

## Step 2 - Recommended BIOS settings
- Boot
  - Compatibility Support Module
    - Launch CSM → **Disabled**

## Step 3 - iCloud setup
Gets this EFI ready for you to use your own iCloud account on it\
**Full Instructions Soon**
1. Open `config.plist` with your favorite plist editor - I use ProperTree
2. Scroll to the `PlatformInfo` section
3. Follow [this guide](https://dortania.github.io/OpenCore-Post-Install/universal/iservices.html#generate-a-new-serial) to generate your serials and place them in the correct location.
Do not worry about networking/en0 or stuff like that, I've already done that.

## Step 4 - Downloading the EFI
1. Download this repo - Click the green button that says `↓ Code`, then choose a ZIP download
2. Unzip the download if needed
3. Move the `EFI` folder somewhere easy to reach. 

## Step 5 - Transferring to your storage device
### Transferring to a USB installer drive
**Coming very soon**

### Replacing an EFI on an SSD/HDD
#### From macOS
1. Use CorpNewt's [MountEFI](https://github.com/corpnewt/MountEFI) to mount the EFI of your SSD/HDD
2. Navigate to the recently mounted EFI
3. Delete the BOOT and OC folders in there
4. Navigate to my EFI that you just downloaded
5. Put the new BOOT and OC folders from my EFI into where the old folders were.
6. Boot

#### From Windows
**Coming very soon**

## Credits
- everyone developing for the hackintosh community
- the [dortania team](https://github.com/orgs/dortania/people)
