---
layout: default
title: Kernel
parent: Ryzen 5000 Series
grand_parent: Desktop CPUs
nav_order: 5
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
</style>

<a align="center" href=""><img src="../../../../assets/" alt="Screenshot of Kernel Section in ProperTree"></a>

<h1 class="section-title">Kernel</h1>

<h2 class="key-title">Add</h2>

This section of the config is meant to expose the various Kexts in your OC folder. This along with many of the other sections will be auto-filled by simply going to ``File -> OC Clean Snapshot`` and selecting the root OC folder in your USB. This step may have already been done, no need to redo.

This section is where OpenCore is told what kernel extensions, kexts, it should look for and load from the Kexts folder in your OpenCore EFI.
If a kext is not present here, OpenCore will not load it. If a kext is defined here but the file is missing from the folder, OpenCore will stop and inform you of the error.

This is one of the sections that can be automatically filled out in ProperTree by going to ``File -> OC Clean Snapshot`` and selecting your OC folder.

<h2 class="key-title">Block</h2>

Blocks certain Kexts from loading.

<h2 class="key-title">Emulate</h2>

This section allows you to set different information about the CPU to be presented to macOS instead of what usually would be, a process known as "spoofing".
The only setting here important to AMD CPUs is `DummyPowerManagement`, which needs to be enabled for macOS 10.15 Catalina to macOS 12 Monterey. It will have no effect in macOS 13 Ventura or macOS 14 Sonoma. For compatibility with more versions of macOS, this is recommended to be set True.

| Key  | Type | Value |
| ----- | ----- | ----- |
| Cpuid1Data | Data | <> |
| Cpuid1Mask | Data | <> |
| DummyPowerManagement | Boolean | True |
| MaxKernel | String | Placeholder |
| MinKernel | String | Placeholder |

<h2 class="key-title">Force</h2>

Used for loading Kexts off system volume, only relevant for older operating systems where certain kexts are not present in the cache, i.e IONetworkingFamily in 10.6.

<h2 class="key-title">Patch</h2>

Patches both the kernel and Kexts.

<h2 class="key-title">Quirks</h2>

Placeholder Text instructing user what to set.

| Key  | Type | Value | Description 
| ----- | ----- | ----- | ----- |
| AppleCpuPmCfgLock | Boolean | False | Should be set False. This is a workaround for certain firmwares when running macOS 12 and earlier on Intel CPUs. This does not apply to AMD CPUs.
| AppleXcpmCfgLock | Boolean | False | Should be set False. A workaround similar to the above. Does not apply to AMD CPUs. |
| AppleXcpmExtraMsrs | Boolean | False | Should be set False. Related to the above. Does not apply to AMD CPUs. |
| AppleXcpmForceBoost | Boolean | False | Should be set False. This quirk forces Intel CPUs to run at maximum speed at all times, potentially increasing performance and reducing CPU lifespan slightly. Does not apply to AMD CPUs. |
| CustomPciSerialDevice | Boolean | False | Should be set False. This quirk allows control over how the macOS kernel interacts with serial ports and can be ignored by most users. |
| CustomSMBIOSGuid | Boolean | True | Recommended set True. When used together with the PlatformInfo quirk `UpdateSMBIOSMode` set as Custom, it allows booting of Windows through OpenCore's bootpicker without the risk of losing Windows activation. Can break Bootcamp functionality on genuine Macs. |
| DisableIoMapper | Boolean | False | Should be set False. This setting controls part of Intel virtualisation technologies in the macOS kernel. Does not apply to AMD. |
| DisableIoMapperMapping | Boolean | False | Should be set False. This setting works around some issues with Intel virtualisation in specific circumstances. Does not apply to AMD. |
| DisableLinkeditJettison | Boolean | True | Should be set True. Helps Lilu.kext and possibly other kexts work properly without `keepsyms=1` in your boot-args. |
| DisableRtcChecksum | Boolean | False | Should be set False. This quirk can fix issues when rebooting or shutting down from macOS, where the system resets or starts back up into Safe Mode. |
| ExtendBTFeatureFlags | Boolean | False | Should be set False to start with. This quirk can force enable some Bluetooth functionality in macOS. This is not required for all Bluetooth adapters. You will need to research your particular adapter to see if this is required. |
| ExternalDiskIcons | Boolean | False | Should be set False. This is a workaround to force drive icons for AHCI disks to appear as internal. It does not actually make macOS see those drives as internal, and a DeviceProperties entry should be used instead if internal SATA drives are shown as removable in macOS. |
| ForceAquantiaEthernet | Boolean | False | Should be set False. This quirk is used to re-enable support for specific Aquantia 10GbE network adapters on Intel systems. Other methods are used to enable these network adapters for AMD based systems. |
| ForceSecureBootScheme | Boolean | False | Should be set False. This is used when macOS is running as a virtual machine in certain instances. Most users can ignore this. |
| IncreasePciBarSize | Boolean | False | Should be set False. This is a workaround for certain firmwares that do not behave correctly with PCI BARs. Does not apply to most users. |
| LapicKernelPanic | Boolean | False | A workaround for kernel panics related to LAPIC. Enable this quirk if you experience those. |
| LegacyCommpage | Boolean | False | Should be set False. This is a workaround for old versions of macOS when used with old CPUs lacking certain features. |
| PanicNoKextDump | Boolean | False | Recommended set False. This quirk prevents full kernel extension information from being included in kernel panic logs. |
| PowerTimeoutKernelPanic | Boolean | False | Recommended set False. This is a workaround for misbehaving devices that would otherwise trip the power change timeout detection and kernel panic introduced in macOS 10.15 Catalina. |
| ProvideCurrentCpuInfo | Boolean | True | MUST be set True for AMD systems and boot will fail without it. Required by the necessary AMD Vanilla kernel patches. |
| SetApfsTrimTimeout | Number | 0 | Recommended set `0`. This controls the trim behaviour for APFS drives during macOS boot. How you should set this will depend on what SSDs you have, with only WD or SanDisk branded SSDs recommended to set this `-1` to enable boot-time trim. |
| ThirdPartyDrives | Boolean | False | Recommended set False. This quirk forces activation of certain features such as SSD trim and hibernation on non-Apple drives. If these features are desired, they can be enabled with other more recommended methods. |
| XhciPortLimit | Boolean | False | MUST be set False. A workaround for older versions of macOS to assist in USB mapping that will cause instability in modern macOS. Current methods of USB mapping do not require this. |

<h2 class="key-title">Scheme</h2>

Placeholder Text instructing user what to set and why, if needed.

These are settings related to booting very old versions of macOS. You can ignore these.

| Key  | Type | Value |
| ----- | ----- | ----- | ----- |
| CustomKernel | Boolean | False |
| FuzzyMatch | Boolean | False |
| KernelArch | String | Auto |
| KernelCache | String | Auto |

<h2 align="center">
  <br>
  <div class="navigation-container">
    <a class="nav-button" href="../04-DeviceProperties/">&larr; Back Page</a>
    <a class="nav-button" href="../06-Misc/">Next Page &rarr;</a>
  </div>
  <br>
</h2>
