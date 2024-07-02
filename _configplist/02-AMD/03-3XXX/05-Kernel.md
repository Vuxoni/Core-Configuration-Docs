---
layout: default
title: Kernel
parent: 3XXX
grand_parent: AMD CPUs
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

<h2 class="key-title">Block</h2>

Blocks certain Kexts from loading.

<h2 class="key-title">Emulate</h2>

Needed for spoofing unsupported CPUs like Pentiums and Celerons.

| Key  | Type | Value |
| ----- | ----- | ----- |
| Cpuid1Data | Data | <> |
| Cpuid1Mask | Data | <> |
| DummyPowerManagement | Boolean | False |
| MaxKernel | String | Placeholder |
| MinKernel | String | Placeholder |

<h2 class="key-title">Force</h2>

Used for loading Kexts off system volume, only relevant for older operating systems where certain kexts are not present in the cache, i.e IONetworkingFamily in 10.6.

<h2 class="key-title">Patch</h2>

Patches both the kernel and Kexts.

<h2 class="key-title">Quirks</h2>

Placeholder Text instructing user what to set.

| Key  | Type | Value | 
| ----- | ----- | ----- |
| AppleCpuPmCfgLock | Boolean | False |
| AppleXcpmCfgLock | Boolean | False |
| AppleXcpmExtraMsrs | Boolean | False |
| AppleXcpmForceBoost | Boolean | False |
| CustomPciSerialDevice | Boolean | False |
| CustomSMBIOSGuid | Boolean | False |
| DisableIoMapper | Boolean | False |
| DisableIoMapperMapping | Boolean | False |
| DisableLinkeditJettison | Boolean | False |
| DisableRtcChecksum | Boolean | False |
| ExtendBTFeatureFlags | Boolean | False |
| ExternalDiskIcons | Boolean | False |
| ForceAquantiaEthernet | Boolean | False |
| ForceSecureBootScheme | Boolean | False |
| IncreasePciBarSize | Boolean | False |
| LapicKernelPanic | Boolean | False |
| LegacyCommpage | Boolean | False |
| PanicNoKextDump | Boolean | False |
| PowerTimeoutKernelPanic | Boolean | False |
| ProvideCurrentCpuInfo | Boolean | False |
| SetApfsTrimTimeout | Number | 0 |
| ThirdPartyDrives | Boolean | False |
| XhciPortLimit | Boolean | False |

<h2 class="key-title">Scheme</h2>

Placeholder Text instructing user what to set and why, if needed.

| Key  | Type | Value | Description | 
| ----- | ----- | ----- | ----- |
| CustomKernel | Boolean | False | Placeholder |
| FuzzyMatch | Boolean | False | Placeholder |
| KernelArch | String | Auto | Placeholder |
| KernelCache | String | Auto | Placeholder |

<h2 align="center">
  <br>
  <div class="navigation-container">
    <a class="nav-button" href="../04-DeviceProperties/">&larr; Back Page</a>
    <a class="nav-button" href="../06-Misc/">Next Page &rarr;</a>
  </div>
  <br>
</h2>
