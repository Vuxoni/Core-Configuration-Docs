---
layout: default
title: UEFI
parent: Tigerlake
grand_parent: Intel CPUs
nav_order: 9
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

<a align="center" href=""><img src="../../../../assets/" alt="Screenshot of UEFI Section in ProperTree"></a>

<h1 class="section-title">UEFI</h1>

<h2 class="key-title">APFS</h2>

Provide APFS support as configured in the APFS Properties section below.

By default, OpenCore only loads APFS drivers from macOS Big Sur and newer. If you are booting macOS Catalina or earlier, you may need to set a new minimum version/date. Not setting this can result in OpenCore not finding your macOS partition! Running Monterey, Ventura, or even Sonoma, you can skip this section.

| Key  | Type | Value | 
| ----- | ----- | ----- |
| EnableJumpstart | Boolean | False |
| GlobalConnect | Boolean | False |
| HideVerbose | Boolean | False |
| JumpstartHotPlug | Boolean | False |
| MinDate | Number | 0 |
| MinVersion | Number | 0 |

``EnableJumpstart`` loads embedded APFS drivers from APFS containers. An APFS EFI driver is bundled in all bootable APFS containers. This option performs the loading of signed APFS drivers (consistent with the ScanPolicy).

``GlobalConnect`` performs full device connection during APFS loading. Every handle is connected recursively instead of the partition handle connection typically used for APFS driver loading. This may result in additional time being taken but can sometimes be the only way to access APFS partitions on certain firmware, such as those on older HP laptops.

``HideVerbose`` hides verbose output from APFS driver.

``JumpstartHotPlug`` permits APFS USB hot plug which enables loading APFS drivers, both at OpenCore startup and during OpenCore picker display.

``MinDate`` sets the minimal allowed APFS driver date.

``MinVersion`` sets the minimal allowed APFS driver version.

Placeholder text telling user what options are needed, and why. Delete those which are not required.

<h2 class="key-title">AppleInput</h2>

Configure the re-implementation of the Apple Event protocol described in the AppleInput Properties section below.

| Key  | Type | Value | 
| ----- | ----- | ----- |
| AppleEvent | String | Placeholder |
| CustomDelays | Boolean | False |
| GraphicsInputMirroring | Boolean | False |
| KeyInitialDelay | Number | 0 |
| KeySubsequentDelay | Number | 0 |
| PointerDwellClickTimeout | Number | 0 |
| PointerDwellDoubleClickTimeout | Number | 0 |
| PointerDwellRadius | Number | 0 |
| PointerPollMask | Number | 0 |
| PointerPollMax | Number | 0 |
| PointerPollMin | Number | 0 |
| PointerSpeedDiv | Number | 0 |
| PointerSpeedMul | Number | 0 |

``AppleEvent`` determines whether the OpenCore builtin or the OEM Apple Event protocol is used.

``CustomDelays`` enables custom key repeat delays when using the OpenCore re-implementation of the Apple Event protocol. Has no effect when using the OEM Apple implementation (see AppleEvent setting). 

``GraphicsInputMirroring`` toggles Apple’s own implementation of AppleEvent prevents keyboard input during graphics applications from appearing on the basic console input stream.

``KeyInitialDelay`` configures the initial delay before keyboard key repeats in the OpenCore re-implementation of the Apple Event protocol, in units of 10ms. The Apple OEM default value is 50 (500ms).

``KeySubsequentDelay`` configures the gap between keyboard key repeats in the OpenCore re-implementation of the Apple Event protocol, in units of 10ms. The Apple OEM default value is 5 (50ms). 0 is an invalid value for this option (will issue a debug log warning and use 1 instead).

``PointerDwellClickTimeout`` configures pointer dwell-clicking single left click timeout in milliseconds in the OpenCore re-implementation of the Apple Event protocol. Has no effect when using the OEM Apple implementation (see AppleEvent setting).

``PointerDwellDoubleClickTimeout`` configures pointer dwell-clicking single left double click timeout in milliseconds in the OpenCore re-implementation of the Apple Event protocol. Has no effect when using the OEM Apple implementation (see AppleEvent setting).

``PointerDwellRadius`` configures pointer dwell-clicking tolerance radius in pixels in the OpenCore re-implementation of the Apple Event protocol. Has no effect when using the OEM Apple implementation (see AppleEvent setting).

``PointerPollMask`` configures indices of polled pointers.

``PointerPollMax`` configures maximum pointer polling period in ms. 

``PointerPollMin`` configures minimum pointer polling period in ms.

``PointerSpeedDiv`` configures pointer speed divisor in the OpenCore re-implementation of the Apple Event protocol. Has no effect when using the OEM Apple implementation (see AppleEvent setting).

``PointerSpeedMul`` Configure pointer speed multiplier in the OpenCore re-implementation of the Apple Event protocol. Has no effect when using the OEM Apple implementation (see AppleEvent setting).

Placeholder text telling user what options are needed, and why. Delete those which are not required.

<h2 class="key-title">Audio</h2>

Related to AudioDxe settings, for us we'll be ignoring (leave as default). This is unrelated to audio support in macOS. This is mainly for adding back the Chime sound when OpenCore/macOS starts.

| Key  | Type | Value | 
| ----- | ----- | ----- |
| AudioCodec | Number | 0 |
| AudioDevice | String | Placeholder |
| AudioOutMask | Number | 0 |
| AudioSupport | Boolean | False |
| DisconnectHda | Boolean | False |
| MaximumGain | Number | 0 |
| MinimumAssistGain | Number | 0 |
| MinimumAudibleGain | Number | 0 |
| PlayChime | String | Placeholder |
| ResetTrafficClass | Boolean | False |
| SetupDelay | Number | 0 |

``AudioCodec`` address on the specified audio controller for audio support. As an alternative, this value can be obtained from IOHDACodecDevice class in I/O Registry containing it in IOHDACodecAddress field.

``AudioDevice`` is the Device path of the specified audio controller for audio support.

``AudioOutMask``, a Bit field indicating which output channels to use for UEFI sound.

``AudioSupport`` activates audio support by connecting to a backend driver.

``DisconnectHda`` allows you to force disconnect HDA controller before loading drivers.

``MaximumGain`` is the maximum gain to use for UEFI audio, specified in decibels (dB) with respect to amplifier reference level of 0 dB.

``MinimumAssistGain`` is the minimum gain in decibels (dB) to use for picker audio assist.

``MinimumAudibleGain``, the minimum gain in decibels (dB) at which to attempt to play any sound.

``PlayChime`` is a boolean to control the play chime sound at startup.

``ResetTrafficClass`` Set HDA Traffic Class Select Register to TC0. Placeholder text about needing it or not.

``SetupDelay`` is the Audio codec reconfiguration delay in milliseconds.

Placeholder text telling user what options are needed, and why. Delete those which are not required.

<hr>
Continuing UEFI...

| Key  | Type | Value | 
| ----- | ----- | ----- |
| ConnectDrivers | Boolean | False |

``ConnectDrivers`` forces .efi drivers, change to False will automatically connect added UEFI drivers. This can make booting slightly faster, but not all drivers connect themselves. E.g. certain file system drivers may not load.

Placeholder text telling user what options are needed, and why. Delete those which are not required.

<h2 class="key-title">Drivers</h2>

This section of the config is meant to expose the various Drivers in your OC folder. This along with many of the other sections will be auto-filled by simply going to ``File -> OC Clean Snapshot`` and selecting the root OC folder in your USB. This step may have already been done, no need to redo.

<h2 class="key-title">Input</h2>

Apply individual settings designed for input (keyboard and mouse) in the Input Properties section below. Related to boot.efi keyboard passthrough used for FileVault and Hotkey support.

| Key  | Type | Value | 
| ----- | ----- | ----- |
| KeyFiltering | Boolean | False |
| KeyForgetThreshold | Number | 0 |
| KeySupport | Boolean | False |
| KeySupportMode | String | Placeholder |
| KeySwap | Boolean | False |
| PointerSupport | Boolean | False |
| PointerSupportMode | String | Placeholder |
| TimerResolution | Number | 0 |

``KeyFiltering`` can enable keyboard input sanity checking.

``KeyForgetThreshold`` sets treatment of duplicate key presses as held keys if they arrive during this timeout, in 10 ms units. Only applies to systems using KeySupport.

``KeySupport`` enables internal keyboard input translation to AppleKeyMapAggregator protocol.

``KeySupportMode`` sets internal keyboard input translation to AppleKeyMapAggregator protocol mode.

``KeySwap`` swaps Command and Option keys during submission.

``PointerSupport`` Enable internal pointer driver. This option implements standard UEFI pointer protocol (EFI_SIMPLE_POINTER_PROTOCOL) through certain OEM protocols. The option may be useful on Z87 ASUS boards, where EFI_SIMPLE_POINTER_PROTOCOL is defective.

``PointerSupportMode`` Set OEM protocol used for internal pointer driver. Currently the only supported variant is ASUS, using specialised protocol available on certain Z87 and Z97 ASUS boards. More details can be found in general troubleshooting. The value of this property cannot be empty if PointerSupport is enabled.

``TimerResolution`` sets architecture timer resolution.

Placeholder text telling user what options are needed, and why. Delete those which are not required.

<h2 class="key-title">Output</h2>

Apply individual settings designed for output (text and graphics) in the Output Properties section below. Relating to OpenCore's visual output.

| Key  | Type | Value | 
| ----- | ----- | ----- |
| ClearScreenOnModeSwitch | Boolean | False |
| ConsoleFont | String | Placeholder |
| ConsoleMode | String | Placeholder |
| DirectGopRendering | Boolean | False |
| ForceResolution | Boolean | False |
| GopBurstMode | Boolean | False |
| GopPassThrough | String | Placeholder |
| IgnoreTextInGraphics | Boolean | False |
| InitialMode | String | Placeholder |
| ProvideConsoleGop | Boolean | False |
| ReconnectGraphicsOnConnect | Boolean | False |
| ReconnectOnResChange | Boolean | False |
| ReplaceTabWithSpace | Boolean | False |
| Resolution | String | Placeholder |
| SanitiseClearScreen | Boolean | False |
| TextRenderer | String | Placeholder |
| UIScale | Number | 0 |
| UgaPassThrough | Boolean | False |

``ClearScreenOnModeSwitch`` useful when some types of firmware only clear part of the screen when switching from graphics to text mode, leaving a fragment of previously drawn images visible. This option fills the entire graphics screen with black colour before switching to text mode.

``ConsoleFont`` specifies the console font to use for OpenCore Builtin text renderer. The font file must be located in ``EFI/OC/Resources/Font/`` and be 8x16 resolution. Various console fonts can be found online in either .bdf or .hex format. While .bdf can be converted to .hex format using gbdfed (available for Linux or macOS).

``ConsoleMode`` sets console output mode as specified with the WxH (e.g. 80x24) formatted string.

``DirectGopRendering`` Boolean dictates usage for builtin graphics output protocol renderer for console. On certain firmware, such as on the MacPro5,1 this may provide better performance or fix rendering issues. 

``ForceResolution`` Forces Resolution to be set in cases where the desired resolution is not available by default, such as on legacy Intel GMA and first generation Intel HD Graphics (Ironlake/Arrandale). Setting Resolution to Max will try to pull the largest available resolution from the connected display's EDID.

``GopBurstMode`` enables write-combining (WC) caching for GOP memory, if system firmware has not already enabled it.

``GopPassThrough`` provides GOP protocol instances on top of UGA protocol instances.

``IgnoreTextInGraphics`` for some types of firmware output text onscreen in both graphics and text mode. This is typically unexpected as random text may appear over graphical images and cause UI corruption. Setting this option to true will discard all text output if console control is not in Text mode.

``InitialMode`` selects the internal ConsoleControl mode in which TextRenderer will operate.

``ProvideConsoleGop`` ensures GOP (Graphics Output Protocol) on console handle. macOS bootloader requires GOP or UGA (for 10.4 EfiBoot) to be present on console handle, yet the exact location of the graphics protocol is not covered by the UEFI specification. This option will ensure GOP and UGA, if present, are available on the console handle.

``ReconnectGraphicsOnConnect`` reconnects all graphics drivers during driver connection.

``ReconnectOnResChange`` reconnects console controllers after changing screen resolution.

``ReplaceTabWithSpace`` is a boolean for types of firmware that do not print tab characters or everything that follows them, causing difficulties in using the UEFI Shell's builtin text editor to edit property lists and other documents. This option makes the console output spaces instead of tabs.

``Resolution`` sets console output screen resolution. Set to WxH@Bpp (e.g. 1920x1080@32) or WxH (e.g. 1920x1080) formatted string to request custom resolution from GOP if available.

``SanitiseClearScreen`` for some types of firmware that reset screen resolutions to a failsafe value (such as 1024x768) on the attempts to clear screen contents when large display (e.g. 2K or 4K) is used. This option attempts to apply a workaround.

``TextRenderer`` chooses renderer for text going through standard console output. Currently two renderers are supported: Builtin and System.

``UIScale`` User interface scaling factor.

``UgaPassThrough`` Provide UGA protocol instances on top of GOP protocol instances. Some types of firmware do not implement the legacy UGA protocol but this may be required for screen output by older EFI applications such as EfiBoot from 10.4.

Placeholder text telling user what options are needed, and why. Delete those which are not required.

<h2 class="key-title">ProtocolOverrides</h2>

Force builtin versions of certain protocols described in the ProtocolOverrides Properties section below. Mainly relevant for Virtual Machines, legacy Macs and FileVault users.

| Key  | Type | Value | 
| ----- | ----- | ----- |
| AppleAudio | Boolean | False |
| AppleBootPolicy | Boolean | False |
| AppleDebugLog | Boolean | False |
| AppleEg2Info | Boolean | False |
| AppleFramebufferInfo | Boolean | False |
| AppleImageConversion | Boolean | False |
| AppleImg4Verification | Boolean | False |
| AppleKeyMap | Boolean | False |
| AppleRtcRam | Boolean | False |
| AppleSecureBoot | Boolean | False |
| AppleSmcIo | Boolean | False |
| AppleUserInterfaceTheme | Boolean | False |
| DataHub | Boolean | False |
| DeviceProperties | Boolean | False |
| FirmwareVolume | Boolean | False |
| HashServices | Boolean | False |
| OSInfo | Boolean | False |
| PciIo | Boolean | False |
| UnicodeCollation | Boolean | False |

``AppleAudio`` replaces Apple audio protocols with builtin versions.

``AppleBootPolicy`` replaces the Apple Boot Policy protocol with a builtin version. This may be used to ensure APFS compatibility on VMs and legacy Macs.

``AppleDebugLog`` replaces the Apple Debug Log protocol with a builtin version.

``AppleEg2Info`` Replaces the Apple EFI Graphics 2 protocol with a builtin version.

``AppleFramebufferInfo`` replaces the Apple Framebuffer Info protocol with a builtin version. This may be used to override framebuffer information on VMs and legacy Macs to improve compatibility with legacy EfiBoot such as the one in Mac OS X 10.4.

``AppleImageConversion`` replaces the Apple Image Conversion protocol with a builtin version

``AppleImg4Verification`` Replaces the Apple IMG4 Verification protocol with a builtin version. This protocol is used to verify im4m manifest files used by Apple Secure Boot.

``AppleKeyMap`` replaces Apple Key Map protocols with builtin versions.

``AppleRtcRam`` replaces the Apple RTC RAM protocol with a builtin version.

``AppleSecureBoot`` replaces the Apple Secure Boot protocol with a builtin version.

``AppleSmcIo`` replaces the Apple SMC I/O protocol with a builtin version. This protocol replaces the legacy VirtualSmc UEFI driver, and is compatible with any SMC kernel extension. However, in case the FakeSMC kernel extension is used, manual NVRAM key variable addition may be needed.

``AppleUserInterfaceTheme`` replaces the Apple User Interface Theme protocol with a builtin version.

``DataHub`` replaces the Data Hub protocol with a builtin version.

``DeviceProperties`` replaces the Device Property protocol with a builtin version. This may be used to ensure full compatibility on VMs and legacy Macs.

``FirmwareVolume`` wraps Firmware Volume protocols, or installs a new version, to support custom cursor images for FileVault 2. Set to true to ensure FileVault 2 compatibility on anything other than on VMs and legacy Macs.

``HashServices`` replaces Hash Services protocols with builtin versions. Set to true to ensure FileVault 2 compatibility on platforms with defective SHA-1 hash implementations. This can be determined by an invalid cursor size when UIScale is set to 02. Platforms earlier than APTIO V (Haswell and older) are typically affected.

``OSInfo`` replaces the OS Info protocol with a builtin version. This protocol is typically used by the firmware and other applications to receive notifications from the macOS bootloader.

``PciIo`` replaces functions in CpuIo and PciRootBridgeIo with 64-bit MMIO compatible ones to fix Invalid Parameter when using 4G Decoding. This affects UEFI drivers such as AudioDxe which access 64-bit MMIO devices. Platforms earlier than APTIO V (Haswell and older) are typically affected.

``UnicodeCollation`` replaces unicode collation services with builtin versions. Set to true to ensure UEFI Shell compatibility on platforms with defective unicode collation implementations. Legacy Insyde and APTIO platforms on Ivy Bridge, and earlier, are typically affected.

Placeholder text telling user what options are needed, and why. Delete those which are not required.

<h2 class="key-title">Quirks</h2>

Apply individual firmware quirks described in the Quirks Properties section below. Relating to quirks with the UEFI environment.

| Key  | Type | Value | 
| ----- | ----- | ----- |
| ActivateHpetSupport | Boolean | False |
| DisableSecurityPolicy | Boolean | False |
| EnableVectorAcceleration | Boolean | False |
| EnableVmx | Boolean | False |
| ExitBootServicesDelay | Number | 0 |
| ForceOcWriteFlash | Boolean | False |
| ForgeUefiSupport | Boolean | False |
| IgnoreInvalidFlexRatio | Boolean | False |
| ReleaseUsbOwnership | Boolean | False |
| ReloadOptionRoms | Boolean | False |
| RequestBootVarRouting | Boolean | False |
| ResizeGpuBars | Number | 0 |
| ResizeUsePciRbIo | Boolean | False |
| ShimRetainProtocol | Boolean | False |
| TscSyncTimeout | Number | 0 |
| UnblockFsConnect | Boolean | 0 |

``ActivateHpetSupport`` activates HPET support. Older boards like ICH6 may not always have HPET setting in the firmware preferences, this option tries to force enable it.

``DisableSecurityPolicy`` disables platform security policy. Note: This setting disables various security features of the firmware, defeating the purpose of any kind of Secure Boot. Do NOT enable if using UEFI Secure Boot.

``EnableVectorAcceleration`` enables AVX vector acceleration of SHA-512 and SHA-384 hashing algorithms. Note: This option may cause issues on certain laptop firmwares, including Lenovo.

``EnableVmx`` enables Intel virtual machine extensions. Required to allow virtualization in Windows on some Mac hardware. VMX is enabled or disabled and locked by BIOS before OpenCore starts on most firmware. Use BIOS to enable virtualization where possible. 

``ExitBootServicesDelay`` adds delay in microseconds after EXIT_BOOT_SERVICES event.

``ForceOcWriteFlash`` enables writing to flash memory for all OpenCore-managed NVRAM system variables

``ForgeUefiSupport`` implements partial UEFI 2.x support on EFI 1.x firmware. This setting allows running some software written for UEFI 2.x firmware, such as NVIDIA GOP Option ROMs, on hardware with older EFI 1.x firmware (e.g. MacPro5,1).

``IgnoreInvalidFlexRatio`` Some types of firmware (such as APTIO IV) may contain invalid values in the MSR_FLEX_RATIO (0x194) MSR register. These values may cause macOS boot failures on Intel platforms. Note: While the option is not expected to harm unaffected firmware, its use is recommended only when specifically required.

``ReleaseUsbOwnership`` attempts to detach USB controller ownership from the firmware driver. While most types of firmware manage to do this properly, or at least have an option for this, some do not. As a result, the operating system may freeze upon boot. Not recommended unless specifically required.

``ReloadOptionRoms`` enables query of PCI devices and reload their Option ROMs if available. For example, this option allows reloading NVIDIA GOP Option ROM on older Macs after the firmware version is upgraded via ForgeUefiSupport.

``RequestBootVarRouting`` requests redirect of all Boot prefixed variables from EFI_GLOBAL_VARIABLE_GUID to OC_VENDOR_VARIABLE_GUID.

``ResizeGpuBars`` configures GPU PCI BAR sizes. This quirk sets GPU PCI BAR sizes as specified or chooses the largest available below the ResizeGpuBars value. The specified value follows PCI Resizable BAR spec. Use 0 for 1 MB, 1 for 2 MB, 2 for 4 MB, and so on up to 19 for 512 GB.

``ResizeUsePciRbIo`` uses PciRootBridgeIo for ResizeGpuBars and ResizeAppleGpuBars.

``ShimRetainProtocol`` requests Linux Shim to keep protocol installed for subsequent image loads.

``TscSyncTimeout`` attempts to perform TSC synchronisation with a specified timeout.

``UnblockFsConnect`` can be used on some types of firmware that block partition handles by opening them in By Driver mode, resulting in an inability to install File System protocols. Note: This quirk is useful in cases where unsuccessful drive detection results in an absence of boot entries.

Placeholder text telling user what options are needed, and why. Delete those which are not required.

<h2 class="key-title">ReservedMemory</h2>

Used for exempting certain memory regions from OSes to use, mainly relevant for Sandy Bridge iGPUs or systems with faulty memory. 
Use of this quirk is not covered in this guide. Docs in progress in General Troubleshooting.

<h2 align="center">
  <br>
  <div class="navigation-container">
    <a class="nav-button" href="../08-PlatformInfo/">&larr; Back Page</a>
    <a class="nav-button" href="../10-Completion/">Next Page &rarr;</a>
  </div>
  <br>
</h2>
