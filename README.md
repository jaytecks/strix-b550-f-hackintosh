# STRIX B550-F GAMING Hackintosh
My EFI files for my desktop hack. Motherboard is an ASUS Strix B550-F GAMING

## Important info
- Based on OpenCore 0.6.0
- **As of 08/06/20, can not boot**

# HELP NEEDED
Help is needed to start debugging macOS' boot process on this board!
If you know the pinout to the five pin `COM_DEBUG` header shown here:

![image of header](F47EA593-2588-4280-9741-47D0BFC46C25.jpeg)

please get in touch with me on Discord at:
`✿ Weeb ThatsNiceGuy#7991`

## Intended system config
- An ASUS Strix B550-F GAMING motherboard
- AMD Ryzen 5 3600 CPU
- Reference Gigabyte RX Vega 56 in first PCIe x16 slot
- Apple AirPort BCM943602CS wireless card in second PCIe x16 slot

## Recommended BIOS settings
**Boot**
- Secure Boot 
  - Secure Boot → Off
  - OS Type → Windows 10
- CSM
  - Launch CSM → Disabled

## "features"
- Based on OpenCore 0.5.9

## Known issues
- **Doesn't boot**
- Sidecar doesn't work - [See here](https://github.com/AMD-OSX/bugtracker/issues/1)
- Apple Watch simulator in Xcode doesn't work (normal for AMD hacks apparently)

## To-do list

**High priority**
- [ ] Get macOS Catalina booting successfully
- [ ] Get system perfectly running Catalina (WiFi, audio, etc)

**Medium priority**

no medium priority stuff yet

**Low priority**
- [ ] Get macOS Big Sur booting successfully

## Credits
- everyone developing for the hackintosh community
- the [dortania team](https://github.com/orgs/dortania/people)
