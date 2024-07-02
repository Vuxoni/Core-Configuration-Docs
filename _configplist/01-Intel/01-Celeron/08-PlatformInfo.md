---
layout: default
title: PlatformInfo
parent: Celeron
grand_parent: Intel CPUs
nav_order: 8
has_children: false
has_toc: false
---

<style>
  .navigation-container {
    display: flex;
    justify-content: space-between;
    align-items: center;
    width: 100%;
  }
  
  .nav-button {
    margin: 10px;
  }

  .section-title{
    text-align: center
  }

  .key-title{
    text-align: left
  }

  .key-entry{
    text-align: center
  }
</style>

<a align="center" href=""><img src="../../../../assets/" alt="Screenshot of PlatformInfo Section in ProperTree"></a>

<h1 class="section-title">Platform Info</h1>

| Key  | Type | Value | 
| ----- | ----- | ----- |
| Automatic | Boolean | True |
| CustomMemory | Boolean | False |

``Automatic`` can be left as default.

``CustomMemory`` can be ignored for now. Documentation in progress.

<h2 class="key-title">Generic</h2>

Placeholder text for this Key.

| Key  | Type | Value | 
| AdviseFeatures | Boolean | False |
| MLB | String | Placeholder |
| MaxBIOSVersion | Boolean | False |
| ProcessorType | Number | 0 |
| ROM | Data | <> |
| SpoofVendor | Boolean | False |
| SystemMemoryStatus | String | Placeholder |
| SystemProductName | String | Placeholder |
| SystemSerialNumber | String | Placeholder |
| SystemUUID | String | Placeholder |

``AdviseFeatures`` updates FirmwareFeatures with supported bits. Placeholder text explaining if needed or not and why.

``MaxBIOSVersion`` sets BIOSVersion to 9999.999.999.999.999, recommended for legacy Macs when using Automatic PlatformInfo, to avoid BIOS updates in unofficially supported macOS versions. Placeholder text explaining if needed or not and why.

``ProcessorType`` sets the detected Processor Type based on the number given derived from [AppleSmBios.h](https://raw.githubusercontent.com/acidanthera/OpenCorePkg/master/Include/Apple/IndustryStandard/AppleSmBios.h). Convert the Hex to Decimal and use that as the Number value.

``SpoofVendor`` sets SMBIOS vendor fields to Acidanthera. It can be dangerous to use "Apple" in SMBIOS vendor fields for reasons outlined in the SystemManufacturer description. However, certain firmware may not provide valid values otherwise, which could obstruct the operation of some software.

``SystemMemoryStatus`` indicates whether system memory is upgradable in PlatformFeature. This controls the visibility of the Memory tab in "About This Mac".

<hr>

At this point in the guide, you'll need to open a terminal and an instance of [GenSMBIOS](https://github.com/corpnewt/GenSMBIOS). 

To get started if you haven't already, select Option 1 for downloading MacSerial and Option 3 for generating SMBIOS.

For this example, we'll choose the MacModel0,0 SMBIOS.

This will give us output similar to the following:

```
  #######################################################
 #               MacModel0,0 SMBIOS Info                 #
#######################################################

Type:         MacModel0,0
Serial:       000000000000
Board Serial: 000000000000000000
SmUUID:       00000000-0000-0000-0000-000000000000
Apple ROM:    000000000000

Press [enter] to return...
```

{: .headsup }
Make sure that you are using an invalid serial number! When visiting the [Check Device Coverage](https://checkcoverage.apple.com/) page on Apple's website, your serial number should not report an exising Mac, and you should get an error message such as "Please enter a valid serial number".

To fill out the information on your config.plist, refer to the following chart to convert across.

| GenSMBIOS | config.plist | 
| ----- | ----- |
| Board Serial | MLB |
| Apple ROM | ROM |
| Type | SystemProductName |
| Serial | SystemSerialNumber |
| SmUUID | SystemUUID |

<hr>
Continuing PlatformInfo...

| Key  | Type | Value | 
| ----- | ----- | ----- |
| UpdateDataHub | Boolean | False |
| UpdateNVRAM | Boolean | False |
| UpdateSMBIOS | Boolean | False |
| UpdateSMBIOSMode | String | Placeholder |
| UseRawUuidEncoding | Boolean | False |

``UpdateDataHub`` updates Data Hub fields. We can leave this default.

``UpdateNVRAM`` updates NVRAM fields related to platform information. We can leave this default.

``UpdateSMBIOS`` updates SMBIOS fields. We can leave this default.

``UpdateSMBIOSMode`` replaces the tables with newly allocated EfiReservedMemoryType. We can leave this default.

``UseRawUuidEncoding`` uses raw encoding for SMBIOS UUIDs. We can leave this default.

<h2 align="center">
  <br>
  <div class="navigation-container">
    <a class="nav-button" href="../07-NVRAM/">&larr; Back Page</a>
    <a class="nav-button" href="../09-UEFI/">Next Page &rarr;</a>
  </div>
  <br>
</h2>
