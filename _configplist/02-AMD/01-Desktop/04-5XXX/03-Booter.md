---
layout: default
title: Booter
parent: Ryzen 5000 Series
grand_parent: Desktop CPUs
nav_order: 3
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

<a align="center" href=""><img src="../../../../assets/" alt="Screenshot of Booter Section in ProperTree"></a>

<h1 class="section-title">Booter</h1>

<h2 class="key-title">MmioWhitelist</h2>

This section defines memory regions for when the DevirtualiseMmio quirk is enabled.
The function and purpose of the whitelist is discussed in >>INSERT LINK TO MMIOWHITELIST EXPLAINER HERE<<

Most Ryzen 5000-compatible motherboards do not require this.


<h2 class="key-title">Patch</h2>

This contains general patches, for us, we can ignore this.

<h2 class="key-title">Quirks</h2>

Placeholder Text instructing user what to set.
As the name implies, this section is used to adapt OpenCore to whatever quirks your motherboard's firmware has to achieve a successful boot of macOS.
The required quirks will be different depending on which motherboard is used and how recent the firmware is. Newer firmwares tend to support memory attributes tables, MATs, while older ones do not. The support for MATs will determine how to set certain quirks.

THE BELOW IS BASED ON MY X570 BOARD AND WILL NEED DIFFERENT OPTIONS FOR OTHER BOARDS ADDED

| Quirk  | Value | Description | 
| ----- | ----- | ----- |
| AllowRelocationBlock | False | Should be set False except for very rare situations where the normal kernel slide mechanism cannot be used, or when booting macOS 10.7 or older. |
| AvoidRuntimeDefrag | True | Needs to be set True on nearly all PC firmwares as it protects essential firmware services from being overridden during macOS boot. |
| DevirtualiseMmio | False | Should be set False for most firmwares. If other efforts to get macOS to boot fail, this may help. Must be used with an MMIO whitelist as described above. |
| DisableSingleUser | False | Recommended False. This enables or disables the use of Single User mode in macOS. If Apple Secure Boot is set up, this quirk will have no effect as Single User Mode will always be disabled. |
| DisableVariableWrite | False | Should be set False. Prevents macOS from writing to NVRAM, which is normally required. |
| DiscardHibernateMap | False | Should be set False. Affects system behaviour when resuming from Hibernation/S4 Sleep. |
| EnableSafeModeSlide | True | Recommended True. Allows OpenCore to set a working slide value when booting into Safe Mode. |
| EnableWriteUnprotector | False | If your firmware supports MATs, this should be set False while firmwares without MAT support need this set True. Certain misbehaving firmwares with MAT support may also need this set False. |
| FixupAppleEfiImages | False | Should be set False unless seeing boot failures with legacy Mac OS X 10.12 or older. |
| ForceBooterSignature | False | Should be set False. Used with real Mac firmwares. |
| ForceExitBootServices | False | Should be set False. In very rare circumstances, this can help force boot only if nothing else helps. |
| ProtectMemoryRegions | False | Should be set False. Some rare firmwares may need this set True to fix issues with waking from sleep, boot or other problems. |
| ProtectSecureBoot | False | Should be set False. Setting this to True will enable reporting of write attempts to firmware Secure Boot variables in NVRAM. Keep set to False if it causes issues. |
| ProtectUefiServices | False | Should be set False. This quirk when set True may help other quirks related to memory management such as DevirtualiseMmio or RebuildAppeMemoryMap work correctly. |
| ProvideCustomSlide | True | Should be set True. Many firmwares will not support the use of all slide values and this quirk ensures that only usable slide values will be made available to macOS |
| ProvideMaxSlide | `0` | Should be set to the number `0`. Some firmwares may misbehave even with ProvideCustomSlide set True and require further limiting of slide values. See Configuration.pdf for how to use this. |
| RebuildAppleMemoryMap | False | Should be set True when MAT support is available. If the firmware does not support MATs or misbehaves, set this False. |
| ResizeAppleGpuBars | `0` | This quirk needs to be set to the number `0` when Resizable BAR support is enabled in firmware. If Resizable BAR is not enabled on the system, set to `-1`. |
| SetupVirtualMap | False | This should be set False for most recent firmwares, however some systems will need this set True. If everything else seems correct and boot still fails, try changing this. |
| SignalAppleOS | False | Should be set False. Used with real Macs. |
| SyncRuntimePermissions | True | Should be set True. One of the quirks related to MAT support in firmware. If MAT support is missing or if the firmware misbehaves, set False. |

<h2 align="center">
  <br>
  <div class="navigation-container">
    <a class="nav-button" href="../02-ACPI/">&larr; Back Page</a>
    <a class="nav-button" href="../04-DeviceProperties/">Next Page &rarr;</a>
  </div>
  <br>
</h2>
