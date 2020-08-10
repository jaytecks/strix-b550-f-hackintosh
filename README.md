# STRIX B550-F GAMING Hackintosh
My EFI files for my desktop hack. Motherboard is an ASUS Strix B550-F GAMING

## Important info
- Based on OpenCore 0.6.0
- **EFI now mostly working!**

## What works
- Full support for Catalina 10.15
- Audio
- Ethernet
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
- [ ] Get system perfectly running Catalina (WiFi, audio, etc)

**Medium priority**

no medium priority stuff yet

**Low priority**
- [ ] Get macOS Big Sur booting successfully

# Installation and Usage
Use my EFI with this guide

## Step 1 - Intended system config 
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
  - Try not to put an NVMe SSD in this slot, as it will reduce the amount of PCIe lanes available to your GPU

**You must follow the pcie slot placements to use this EFI as-is. If you would like to put things in different slots, you'll have to configure DeviceProperties yourself.**

## Step 2 - Recommended BIOS settings
**Coming very soon**

## Step 3 - Serial Number
**Coming very soon**

## Step 4 - Transferring to your storage device
### Transferring to a USB installer drive
**Coming very soon**

### Replacing an EFI on an SSD/HDD
**Coming very soon**

## Credits
- everyone developing for the hackintosh community
- the [dortania team](https://github.com/orgs/dortania/people)
