---
layout: default
title: Miscellaneous
parent: Tigerlake
grand_parent: Intel CPUs
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

Placeholder Text

| Key  | Type | Value | 
| ----- | ----- | ----- |
| ConsoleAttributes | Number | 0 |
| HibernateMode | String | Placeholder |
| HibernateSkipsPicker | Boolean | False |
| HideAuxiliary | Boolean | False |
| InstanceIdentifier | String | Placeholder |
| LauncherOption | String | Placeholder |
| LauncherPath | String | Placeholder |
| PickerAttributes | Number | 0 |
| PickerAudioAssist | Boolean | False |
| PickerMode | String | Placeholder |
| PickerVariant | String | Placeholder |
| PollAppleHotKeys | Boolean | False |
| ShowPicker | Boolean | False |
| TakeoffDelay | Number | 0 |
| Timeout | Number | 0 |

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
