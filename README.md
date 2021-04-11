# STRIX B550-F GAMING Hackintosh
My EFI files for my desktop hack. Motherboard is an ASUS Strix B550-F GAMING

# UPDATED FILES WILL BE ADDED SOON! PLEASE WAIT UNTIL THEN UNTIL TO USE THIS EFI!

[Help downloading or using this EFI](https://github.com/ThatsNiceGuy/strix-b550-f-hackintosh/blob/master/README.md#installation-and-usage)
## What works
- Full support for Big Sur 11.2.3 and OpenCore 0.6.7
  - Update to OpenCore 0.6.8 is coming later
- Audio
- Ethernet
- USB (fully mapped, incl. USB-C!)
- Wi-Fi if you have a wireless card
- Bluetooth if you have a wireless card
- All iCloud and Continuity features if you have a macOS supported wireless card

## Known issues
- Sidecar doesn't work - [See here](https://github.com/AMD-OSX/bugtracker/issues/1)
- Apple Watch simulator in Xcode doesn't work (normal for AMD hacks apparently)

## To-do list

**High priority**


**Medium priority**
- [ ] Ensure sleep is working

**Low priority**
- [ ] Check DRM for Apple TV+, Netflix, etc.
  
# Installation and Usage

## Requirements
- ProperTree
- Ability to read instructions
- Good knowledge of navigating filesystems

**Table of contents**
- [Step 1 - Intended system config](https://github.com/ThatsNiceGuy/strix-b550-f-hackintosh/blob/master/README.md#step-1---intended-system-config)
- [Step 2 - Recommended BIOS settings](https://github.com/ThatsNiceGuy/strix-b550-f-hackintosh/blob/master/README.md#step-2---recommended-bios-settings)
- [Step 3 - iCloud setup]()
- [Step 4 - Downloading the EFI]()
- [Step 5 - Transferring to your storage device]()

## Step 1 - Intended system config
**What hardware is supported in my config**

- Motherboard
  - ASUS ROG STRIX B550-F GAMING (Non WiFi)
- CPU
  - Any Ryzen CPU that is compatible with this board
    - Ryzen APUs should not be used, as they have some issues.
- PCIe x1 Gen 3 slot 3
  - Apple Broadcom BCM943602CS wireless card in appropriate adapter
    - You can use any other supported wireless card here, or even forego it entirely.
    - Any device in this slot will be marked as `builtin`.
- M.2 slot 1 (PCIe x4 Gen 4)
  - Sabrent Rocket 2TB NVMe SSD
    - Any device in this slot will be marked as `builtin`.
- M.2 slot 2 (PCIe x4 Gen 3)
  - Samsung 960 EVO NVMe SSD
    - Any device in this slot will be marked as `builtin`.
- SATA devices
  - SATA devices are untested as I don't use any SATA hard drives or SATA SSDs in my PC. I see no reason why they wouldn't work.

This next section is a bit weird, as I use two GPUs in my PC, one is an RTX 3080 and one is a GTX 770. If you would like more details, [you can click here](https://github.com/ThatsNiceGuy/ThatsNiceGuy/blob/master/RTX3080%2BGTX770-macos.md).

- PCIe x16 Gen 4 slot 1
  - ASUS ROG STRIX GeForce RTX 3080 OC 10GB
    - This is an unsupported GPU in all versions of macOS and as such it has been disabled using the DeviceProperties method. This means that any device you put in this slot will be disabled! If you need to put a supported GPU in this slot, you must remove the **\<TBA>** entry in the DeviceProperties section of the `config.plist`! 
- PCIe x16 Gen 3 slot 2
  - MSI Twin Frozr GTX 770 GAMING 2GB OC

If you only have one macOS-supported GPU in your PC, to be able to put a GPU in the first PCIe slot you can remove the **\<TBA>** entry in the DeviceProperties section of the `config.plist` like this:

***ADD IMAGE LATER***

**You must follow the pcie slot placements to use this EFI as-is. If you would like to put things in different slots, you'll have to configure DeviceProperties yourself.**

## Step 2 - Recommended BIOS settings
- Boot
  - Compatibility Support Module
    - Launch CSM → **Disabled**
- Advanced
  - PCI Configuration
    - Above 4G Decoding → **Enabled**
    - Resizable BAR<sup>(if present)</sup> → **Auto**

More needed but TBA

## Step 3 - iCloud setup
Gets this EFI ready for you to use your own iCloud account on it\
**Full Instructions Soon**
1. Open `config.plist` with ProperTree
2. Scroll to the `PlatformInfo` section
3. Follow [this guide](https://dortania.github.io/OpenCore-Post-Install/universal/iservices.html#generate-a-new-serial) to generate your serials and place them in the correct location.
Do not worry about networking/en0 or stuff like that, I've already done that.

## Step 4 - Downloading the EFI

TBA

## Step 5 - Transferring to your storage device
### Transferring to a USB installer drive

TBA

### Replacing/Adding an EFI to an SSD/HDD
**I am not responsible if you nuke your data.**
#### From macOS
ified 
1. Ensure the USB drive with your functional EFI is plugged in.
2. Use the latest version of CorpNewt's MountEFI to mount the EFI partiton of the USB drive.
3. Repeat and mount the EFI partition of the drive you intent to place the EFI onto. (This will typically be the drive you installed macOS to.
4. Instructions will be finished later

#### From Windows

1. Ensure the USB drive with your functional EFI is plugged in.
2. Open a Command Prompt, type in `diskpart`, press Enter and click Yes.
3. Type `list disk`, then press Enter.
4. From here you must identify which drive is your USB drive based off the capacity.
5. Enter in `sel disk x` where `x` is the number you identified to be your USB drive.
6. Enter in `list vol` then identify the one marked 'EFI' or that is around 200MB in size.
7. Enter in `sel vol x` where `x` is the number you identified to be the EFI partition.
8. Enter in `ass letter=X:` where `X` is the drive letter you want to assign it. I typically use Y.
9. Repeat steps 3-8 for your internal hard drive/SSD.
10. Instructions will be finished later.


Note: To remove these drive letter assignments, do step 2 then run **/<TBA>**

## Credits
- everyone developing for the hackintosh community
- the [dortania team](https://github.com/orgs/dortania/people)

## License
TBA
