---
layout: default
title: Booter
nav_order: 2 
parent: Explanations
---

## MmioWhitelist

This section defines memory regions for when the DevirtualiseMmio quirk is enabled.

-- Needed -- 

## Patch

As the name implies, this section is used to adapt OpenCore to whatever quirks your motherboard's firmware has to achieve a successful boot of macOS.

## Quirks

| Quirk                  | Value | Description                                                                                                                                                                                  |
| ---------------------- | ----- | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| AllowRelocationBlock   |       |                                                                                                                                                                                              |
| AvoidRuntimeDefrag     |       | Protects essential firmware services from being overridden during macOS boot.                                                                                                                |
| DevirtualiseMmio       |       | If other efforts to get macOS to boot fail, this may help. -- Add Information about it --                                                                                                    |
| DisableSingleUser      |       | This enables or disables the use of Single User mode in macOS. If Apple Secure Boot is set up, this quirk will have no effect as Single User Mode will always be disabled.                   |
| DisableVariableWrite   |       | Prevents macOS from writing to NVRAM, which is normally required.                                                                                                                            |
| DiscardHibernateMap    |       | Affects system behaviour when resuming from Hibernation/S4 Sleep.                                                                                                                            |
| EnableSafeModeSlide    |       | Allows OpenCore to set a working slide value when booting into Safe Mode. -- Whats a slide value? Safe Mode?                                                                                 |
| EnableWriteUnprotector |       |                                                                                                                                                                                              |
| FixupAppleEfiImages    |       |                                                                                                                                                                                              |
| ForceBooterSignature   |       | Used with real Mac firmwares. -- What do you mean by that?                                                                                                                                   |
| ForceExitBootServices  |       |                                                                                                                                                                                              |
| ProtectMemoryRegions   |       |                                                                                                                                                                                              |
| ProtectSecureBoot      |       | Setting this to True will enable reporting of write attempts to firmware Secure Boot variables in NVRAM.                                                                                     |
| ProtectUefiServices    |       | This quirk when set True may help other quirks related to memory management such as DevirtualiseMmio or RebuildAppleMemoryMap work correctly.                                                |
| ProvideCustomSlide     |       | This quirk ensures that only usable slide values will be made available to macOS                                                                                                             |
| ProvideMaxSlide        |       | Should be set to the number `0`. Some firmwares may misbehave even with ProvideCustomSlide set True and require further limiting of slide values. See Configuration.pdf for how to use this. |
| RebuildAppleMemoryMap  |       | Should be set True when MAT support is available. If the firmware does not support MATs or misbehaves, set this False.                                                                       |
| ResizeAppleGpuBars     |       | This quirk needs to be set to the number `0` when Resizable BAR support is enabled in firmware. If Resizable BAR is not enabled on the system, set to `-1`.                                  |
| SetupVirtualMap        |       | This should be set False for most recent firmwares, however some systems will need this set True. If everything else seems correct and boot still fails, try changing this.                  |
| SignalAppleOS          |       | Should be set False. Used with real Macs.                                                                                                                                                    |
| SyncRuntimePermissions |       | Should be set True. One of the quirks related to MAT support in firmware. If MAT support is missing or if the firmware misbehaves, set False.                                                |
|                        |       |                                                                                                                                                                                              |