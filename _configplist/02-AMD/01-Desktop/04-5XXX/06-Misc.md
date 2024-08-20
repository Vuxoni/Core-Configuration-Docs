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

Helpful for debugging OpenCore boot issues.

| Key  | Type | Value | 
| ----- | ----- | ----- |
| AppleDebug | Boolean | False |
| ApplePanic | Boolean | False |
| DisableWatchDog | Boolean | False |
| DisplayDelay | Number | 0 |
| DisplayLevel | Number | 0 |
| LogModules | String | Placeholder |
| SysReport | Boolean | False |
| Target | Number | 0 |

<h2 class="key-title">Entries</h2>

Used for specifying irregular boot paths that can't be found naturally with OpenCore.

<h2 class="key-title">Security</h2>

Security is pretty self-explanatory, <b>do not skip</b>. We'll be changing the following:

{: .warning }
Optional is a word, you must type it out. It IS case-sensitive.

| Key  | Type | Value | 
| ----- | ----- | ----- |
| AllowSetDefault | Boolean | True |
| ApECID | Number | 0 |
| AuthRestart | Boolean | False |
| BlacklistAppleUpdate | Boolean | False |
| DmgLoading | String | Placeholder |
| EnablePassword | Boolean | False |
| ExposeSensitiveData | Number | 0 |
| HaltLevel | Number | 0 |
| PasswordHash | Data | <> |
| PasswordSalt | Data | <> |
| ScanPolicy | Number | 0 |
| SecureBootModel | String | Default |
| Vault | String | <span style="color:red">Optional</span> |

<h2 class="key-title">Serial</h2>

Used for serial debugging (99% of users do not need to touch this area).

| Key  | Type | Value | 
| ----- | ----- | ----- |
| Init | Boolean | False |
| Override | Boolean | False |

<h2 class="key-title">Tools</h2>

This section of the config is meant to expose the various Tools in your OC folder. This along with many of the other sections will be auto-filled by simply going to ``File -> OC Clean Snapshot`` and selecting the root OC folder in your USB. This step may have already been done, no need to redo.

<h2 align="center">
  <br>
  <div class="navigation-container">
    <a class="nav-button" href="../05-Kernel/">&larr; Back Page</a>
    <a class="nav-button" href="../07-NVRAM/">Next Page &rarr;</a>
  </div>
  <br>
</h2>
