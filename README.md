# STRIX B550-F GAMING Hackintosh
My EFI files for my desktop hack. Motherboard is an ASUS Strix B550-F GAMING

## Important info
- Based on OpenCore 0.6.0
- **Patch released! I'm working on getting the EFI done ASAP, so please be patient!**

## Info from XLNC about the patch
Hi guys !
ok so long story short.
Upon comparing verbose messages i observed that after ACPI tables are acquired and loaded by AppleACPIPlatform, the AppleACPICPU doesnt showup for some reason . So after looking into couple of functions in the AppleACPIPlatform.kext binary, i see that AppleACPICPU looks for ACPI processor objects each with a processor id.

In our ACPI tables usually the processor is declared as `ProcessorObj` which consists of a `ProcessorName` and a `ProcessorID` which then macos uses it to find declared processors in ACPI tables. 
According to ACPI 5.0 spec , they have now provided a newer way of defining processor in ACPI as `DeviceObj` which contains a HID `ACPI0007` to let OS know that its a processor and a UID which acts as a processorID or index in simple words. so now processors can be declared either as ProcessorObj or DeviceObj.
AND since ACPI 6.0 spec the processorObj is deprecated leaving with only DeviceObj as the option.

The problem here is that all B550 boards follow newer ACPI specs where they have their processor declared in DSDT as `DeviceObj` rather than `ProcessorObj` so macOS (AppleACPICPU specifically) looks for ProcessorObj with ProcessorID which isn't used anymore in B550 boards. so when it couldn't find that, it goes around the corner sits there and cry.

Solution:
Re-declare processor in DSDT as ProcessorObj and make macos happy.
it can be done in few ways through hotpatch. so i have created this SSDT based of the ACPI dumps people posted here so might update it in future if needed.

**An SSDT was provided with this message as well.**

## Intended system config
- An ASUS Strix B550-F GAMING motherboard
- AMD Ryzen 5 3600 CPU
- Reference Gigabyte RX Vega 56 in first PCIe x16 slot
- Apple AirPort BCM943602CS wireless card in second PCIe x16 slot

## Recommended BIOS settings
**Coming very soon**

## "features"
???

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
