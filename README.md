# STRIX B550-F GAMING Hackintosh
My EFI files for my desktop hack. Motherboard is an ASUS Strix B550-F GAMING

# UPDATED FILES WILL BE ADDED SOON! PLEASE WAIT UNTIL THEN UNTIL TO USE THIS EFI!

[Help downloading or using this EFI](https://github.com/ThatsNiceGuy/strix-b550-f-hackintosh/blob/master/README.md#installation-and-usage)
## What works
- Full support for Big Sur 11.2.3 and OpenCore 0.6.7 (0.6.8 soon)
- Audio
- Ethernet
- USB (fully mapped!)
- Wi-Fi if you have a wireless card
- Bluetooth if you have a wireless card
- All iCloud and Continuity features if you have a macOS supported wireless card

## Known issues
- Sidecar doesn't work - [See here](https://github.com/AMD-OSX/bugtracker/issues/1)
- Apple Watch simulator in Xcode doesn't work (normal for AMD hacks apparently)

## To-do list

**High priority**

none

**Medium priority**

no medium priority stuff yet

**Low priority**

None
  
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

TBA

**You must follow the pcie slot placements to use this EFI as-is. If you would like to put things in different slots, you'll have to configure DeviceProperties yourself.**

## Step 2 - Recommended BIOS settings
- Boot
  - Compatibility Support Module
    - Launch CSM → **Disabled**

More needed but TBA

## Step 3 - iCloud setup
Gets this EFI ready for you to use your own iCloud account on it\
**Full Instructions Soon**
1. Open `config.plist` with your favorite plist editor - I use ProperTree
2. Scroll to the `PlatformInfo` section
3. Follow [this guide](https://dortania.github.io/OpenCore-Post-Install/universal/iservices.html#generate-a-new-serial) to generate your serials and place them in the correct location.
Do not worry about networking/en0 or stuff like that, I've already done that.

## Step 4 - Downloading the EFI

TBA

## Step 5 - Transferring to your storage device
### Transferring to a USB installer drive

TBA

### Replacing an EFI on an SSD/HDD
#### From macOS

TBA

#### From Windows

TNA

## Credits
- everyone developing for the hackintosh community
- the [dortania team](https://github.com/orgs/dortania/people)
