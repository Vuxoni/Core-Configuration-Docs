---
layout: default
title: Booter
nav_order: 2 
parent: Explanations
---

## MmioWhitelist
Memory-Mapped Input/Output (MMIO) is a method used by computer systems to communicate with peripheral devices (like keyboards, mice, and printers). Instead of using separate I/O instructions, MMIO allows the CPU to interact with devices by reading from and writing to specific memory addresses that are reserved for those devices. In other words: Instead of using special commands to talk to these devices, the CPU treats them like parts of its own memory.

When using MMIO, certain memory addresses are mapped to hardware devices, and these addresses must be protected to ensure that only trusted processes can interact with them. 

In OpenCore, MmioWhitelist allows you to specify which memory addresses are safe for access. To put it simply, Mmio WhiteList allows devices to be passed on to macOS. This is particularly important for systems like (but not limited to) AMD Threadripper or Intel Ice Lake, where improper access can prevent macOS from booting correctly.

[![Booter->MmioWhitelist](/assets/config.plist/Booter->MmioWhitelist.png)](/assets/config.plist/Booter->MmioWhitelist.png)

| Key     | Type    | Description                                                                                                                                                                                                                        |
| ------- | ------- | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Address | Integer | This defines the starting address for the MMIO region that is going to be whitelisted. In theory - Opencore will also attempt to find root addresses of mid-region addresses, however, it's not considered a safe/stable solution. |
| Comment | String  |                                                                                                                                                                                                                                    |
| Enabled | Boolean | Enables whitelisting of the specified regions.                                                                                                                                                                                     |

{: .note }
Finding the regions may be a little bit tricky. In order to display every region that can be devirtualized, OpenCore debug logs are required. -- Add more info later --

## Patch

The Patch subsection is used to apply various patches during the boot process. These patches can address specific memory addresses or fix issues related to your hardware configuration.

## Quirks

### AllowRelocationBlock
###### Type: Boolean

### AvoidRuntimeDefrag
###### Type: Boolean

### DevirtualiseMmio
###### Type: Boolean

### DisableSingleUser
###### Type: Boolean

### DisableVariableWrite
###### Type: Boolean

### DiscardHibernateMap
###### Type: Boolean

### EnableSafeModeSlide
###### Type: Boolean

### EnableWriteUnprotector
###### Type: Boolean

### FixupAppleEfiImages
###### Type: Boolean

### ForceBooterSignature
###### Type: Boolean

### ForceExitBootServices
###### Type: Boolean

### ProtectMemoryRegions
###### Type: Boolean

### ProtectSecureBoot
###### Type: Boolean

### ProtectUefiServices
###### Type: Boolean

### ProvideCustomSlide
###### Type: Boolean

### ProvideMaxSlide
###### Type: Integer

### RebuildAppleMemoryMap
###### Type: Boolean

### ResizeAppleGpuBars
###### Type: Integer

### SetupVirtualMap
###### Type: Boolean

### SignalAppleOS
###### Type: Boolean

### SyncRuntimePermissions
###### Type: Boolean

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