---
layout: default
title: Miscellaneous
parent: Ryzen 5000 Series
grand_parent: Desktop CPUs
nav_order: 6
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

<a align="center" href=""><img src="../../../../assets/" alt="Screenshot of Miscellaneous Section in ProperTree"></a>

<h1 class="section-title">Miscellaneous</h1>

<h2 class="key-title">BlessOverride</h2>

To be filled with plist string entries containing absolute UEFI paths to customised bootloaders such as ``\EFI\debian\grubx64.efi`` for the Debian bootloader.

Other common bootloader paths are:

| OS | Bootloader Path |
| --- | --- |
| Windows | \EFI\Microsoft\Boot\bootmgfw.efi |
| GRUB | Placeholder |
| Placeholder | Placeholder |

You do not have to set this up, and serves as information for those who wish to use the key.

<h2 class="key-title">Boot</h2>

These settings control various boot behaviours for OpenCore and its boot picker.

| Key  | Type | Value | Description |
| ----- | ----- | ----- | ----- |
| ConsoleAttributes | Number | `0` | Allows selecting the colors for OpenCore's text mode display. See Configuration.pdf for details. |
| HibernateMode | String | `None` | Sets which mode OpenCore's hibernation detection should operate in. |
| HibernateSkipsPicker | Boolean | False | When set True, this tells OpenCore to not show its boot picker when waking macOS from hibernation. See Configuration.pdf for details. |
| HideAuxiliary | Boolean | False | Recommended set False. When set True, this will hide certain entries from being initially displayed in the boot picker. Pressing Spacebar will show all detected entries. During initial setup this should be False as to not hide important entries. |
| InstanceIdentifier | String | <Empty> | This allows you to set a unique identifier for different instances of OpenCore. Its purpose and usage is explained in Configuration.pdf |
| LauncherOption | String | `Full` | This controls how OpenCore asks the system firmware to create a boot entry for itself. The Full option will work for most users. For detailed information and other possible settings, see Configuration.pdf |
| LauncherPath | String | `Default` | Should be set to the word `Default`. This setting is used to set the path to any custom bootloader in use for OpenCore. Most users do not need to change this. |
| PickerAttributes | Number | `17` | Recommended set to `17`. OpenCore has various options available for the boot picker, which this setting controls. This setting takes a bitmask made up of various attributes which are explained in Configuration.pdf. In this case, `17` translates to enabling loading icons from macOS volumes to show macOS logos in a graphical boot picker, and enables cursor control. |
| PickerAudioAssist | Boolean | False | When set True, this enabled the boot picker screen reader feature of OpenCore. For this to work, the audio resources must be present in OpenCore's EFI folder and boot picker UEFI audio support enabled. |
| PickerMode | String | Builtin | This setting controls which boot picker mode OpenCore will attempt to use by default. `Builtin` is a text based list of boot options. When set to `External` it allows the use of other boot pickers that allow graphics and other features. This will be covered in more detail later on in this guide. |
| PickerVariant | String | `Auto` | This setting determines the icon set used for the boot picker. Has no effect if there are no icon resources or external boot picker available. |
| PollAppleHotKeys | Boolean | True | Recommended set True. This setting makes certain hotkey combinations easier to use from the OpenCore boot picker. See Configuration.pdf for details. |
| ShowPicker | Boolean | True | Should be set True. When set False, this setting hides the boot picker completely and OpenCore will instead automatically boot whichever boot option is set as the default. |
| TakeoffDelay | Number | `0` | This setting adds a delay, in microseconds, before OpenCore checks which hotkeys are pressed and starting the boot picker. This can make it easier to perform certain hotkey combinations. See Configuration.pdf for further information. |
| Timeout | Number | 0 | Recommended set `0`. This is the time in seconds OpenCore should wait before automatically booting the default boot option. During initial setup this is recommended to be set to `0` to disable automatic booting. |

<h2 class="key-title">Debug</h2>

These are various settings for debugging and logging.

| Key  | Type | Value | Description |
| ----- | ----- | ----- | ----- |
| AppleDebug | Boolean | False | Recommended set True. When enabled, writes the boot.efi debug log to the OpenCore log. Does not apply to the full macOS kernel log. |
| ApplePanic | Boolean | False | Recommended set True. This quirk writes kernel panic logs to the OpenCore root partition, i.e. the EFI partition or USB drive in the event of a macOS kernel panic. See Configuration.pdf for complete details. |
| DisableWatchDog | Boolean | False | Should be set False. Some firmwares have a boot watchdog timer, where boot will be aborted if a boot process takes too long. Setting this True works around such timeouts for particularly slow booting systems. |
| DisplayDelay | Number | 0 | Adds a delay after every line of log output printed to the screen. Can make it easier to read output for troubleshooting, in exchange for much longer boot times. |
| DisplayLevel | Number | 0 | Bitmask for what information to show on screen during OpenCore boot. Requires a suitable `Target` value to be set. |
| LogModules | String | Placeholder | Filters which internal OpenCore components logging is visible on screen and in the OpenCore log files. See Configuration.pdf for complete details. |
| SysReport | Boolean | False | When set True, this quirk asks OpenCore debug builds to write a system report to the OpenCore root partition under a `SysReport` folder. Very useful when debugging and creating ACPI patches and SSDTs on systems that cannot dump ACPI normally such as with the SSDTTime tool. |
| Target | Number | 0 | Recommended set `67`. This is a bitmask that sets the logging OpenCore will perform to the screen and the log file. The value 67 gives comprehensive on-screen and log file logging to aid in troubleshooting. |

<h2 class="key-title">Entries</h2>

This section allows for manually specifing boot entries that OpenCore doesn't find automatically. See Configuration.pdf for complete details.

<h2 class="key-title">Security</h2>

This section controls various parts of both OpenCore and macOS boot security. These settings are very important for booting later versions of macOS and for later on securing the boot process on computers that others may have access to.

{: .warning }
For the Vault setting, `Optional` is a word, you must type it out. It IS case-sensitive. This is also the case for SecureBootModel and its `Disabled` and `Default` settings.

| Key  | Type | Value | Description
| ----- | ----- | ----- | ----- |
| AllowSetDefault | Boolean | True | Recommended set True. This setting allows the default boot entry in the OpenCore boot picker to be changed by holding the +/= key (on a US keyboard) or with the Ctrl+Enter key combination. If the `PollAppleHotKeys` settings in config.plist is enabled, Shift+Enter and Shift+Index combinations can also be used. |
| ApECID | Number | 0 | Recommended set `0`. This value is part of the Apple Secure Boot (distinct from UEFI Secure Boot) process. Its purpose is to prevent taking the drive with macOS on it and booting it on another computer. Using this in macOS 14 Sonoma and later is **not** recommended due to the necessity of disabling SecureBootModel during installation and updates. See Configuration.pdf for complete details. |
| AuthRestart | Boolean | False | Recommended set False. This setting allows for rebooting a FileVault-protected macOS install without re-entering the password. As VirtualSMC achieves this by putting the volume password into the motherboard RTC and NVRAM temporarily during the restart, it may be a security issue and users may want to keep this disabled. |
| BlacklistAppleUpdate | Boolean | False | Should be set False. When enabled, prevents running boot-time updating of firmware for Apple peripherals. Useful if you for some reason don't want your Magic Trackpad firmware updated. |
| DmgLoading | String | Signed | Should be set to the word `Signed`. This tells OpenCore which Disk Images (DMG) are permitted to load. Most users can leave this as `Signed`. |
| EnablePassword | Boolean | False | Should be set False. An in-development protection feature that requires a password for various sensitive operations in OpenCore. See Configuration.pdf for complete details. |
| ExposeSensitiveData | Number | 4 | Recommended set `4`. A bitmask that controls how certain OpenCore and system data is made visible and available. Setting this to `4` will show the OpenCore version in the OpenCore boot picker. |
| HaltLevel | Number | 0 | Should be set `0`. Used to stop (halt) boot when the specified message type is seen. See Configuration.pdf for complete details.|
| PasswordHash | Data | <> | Manually specifies the hash to use for EnablePassword above. You can ignore this. |
| PasswordSalt | Data | <> | Manually specifies the salt used with EnablePassword. You can ignore this.|
| ScanPolicy | Number | 0 | Should be set `0`. This is a bitmask that tells OpenCore where to look for bootable entries. For initial boot, this should be set `0` to tell OpenCore to look for and show all options. |
| SecureBootModel | String | Disabled |  Should be set to the word `Disabled` exactly as shown. When installing and updating macOS 14.4 Sonoma and later, there is an issue where macOS will reboot before it can finish installing if this isn't set `Disabled`. When macOS has finished installing or updating, this can and should be set back to the word `Default` to re-enable boot process security. |
| Vault | String | <span style="color:red">Optional</span> | Should be set to the word `Optional`. This setting controls the OpenCore Vault feature, used for securing OpenCore's part of the boot process. Users wanting to set this up should do so AFTER macOS has been successfully installed. The process will be detailed later on in the guide. See Configuration.pdf for complete details. |

<h2 class="key-title">Serial</h2>

This sections sets up serial debugging of OpenCore and macOS boot. If you don't know what this means you can leave this section alone.
As always, Configuration.pdf has complete details on this feature.

| Key  | Type | Value | 
| ----- | ----- | ----- |
| Init | Boolean | False |
| Override | Boolean | False |

<h2 class="key-title">Tools</h2>

This section lists any tool programs to be booted through OpenCore, and is similar to the previous ACPI>Add and Kernel>Add sections in that it corresponds to files placed in the OpenCore OC folder in your EFI partition, USB drive or other boot device. The best way to fill this out is to place all the desired tools in the correct folder (.e.g /EFI/OC/Tools) and using ProperTree's OC Snapshot feature to allow ProperTree to fill it out for you based on the detected files.
The below is provided as a reference and the options should not need to be changed for most users.
TODO: Link to earlier page explaining tools/ProperTree

| Key  | Type | Value | Description |
| ----- | ----- | ----- | ----- |
| Arguments | String | Placeholder | Boot arguments for a tool can be placed here to be passed to the tool during load. |
| Auxiliary | Boolean | False | This sets the visibility of the tool for the HideAuxiliary setting. If set True here, the tool will be hidden by default when HideAuxiliary is set True. |
| Comment | String | Placeholder | A simple comment field, unused by the system and intended for the user of the config.plist |
| Enabled | Boolean | False | Sets if the tool is active or not. When set False, the tool will not be available in OpenCore's Boot Picker. |
| Flavour | String | Auto | Used by OpenCore to select coSsmetic options for the entry. See `PickerAttributes` under Misc>Entry Properties in Configuration.pdf for complete details. |
| FullNvramAccess | Boolean | False | Controls access to NVRAM. When set True, OpenCore will permit full access to NVRAM by the tool. Use with caution. |
| Name | String | Placeholder | Provides a name for the entry in the OpenCore boot picker. Whatever is written here will be how the tool shows up in the boot picker. |
| Path | String | Placeholder | This informs OpenCore of the path to the tool, relative to the OC/Tools directory. |
| RealPath | Boolean | False | This setting enables informing the tool of its full path when loading. Useful for certain tools but should usually be set False. |
| TextMode | Boolean | False | Sets the use of Text Mode console output for a tool as opposed to the default graphical mode. |

<h2 align="center">
  <br>
  <div class="navigation-container">
    <a class="nav-button" href="../05-Kernel/">&larr; Back Page</a>
    <a class="nav-button" href="../07-NVRAM/">Next Page &rarr;</a>
  </div>
  <br>
</h2>
