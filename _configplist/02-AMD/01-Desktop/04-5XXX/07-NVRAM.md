---
layout: default
title: NVRAM
parent: Ryzen 5000 Series
grand_parent: Desktop CPUs
nav_order: 7
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

<a align="center" href=""><img src="../../../../assets/" alt="Screenshot of NVRAM Section in ProperTree"></a>

<h1 class="section-title">NVRAM</h1>

This section of config.plist controls data placed in NVRAM that is used by both macOS and OpenCore itself. Correct data in NVRAM is critical to the functioning of macOS, and without it macOS may not boot or install at all.

Data stored in NVRAM is known as *variables* and consists of a GUID, a unique identifier, that can have one or more *keys* under itself each with its own associated value.

The variables below are from config.plist and are listed in the order they appear, as the GUIDs, their keys and the variables those keys contain. Each GUID is additionally followed by its name, which is not shown or used in config.plist or in NVRAM.

Configuration.pdf contains more details on possible NVRAM variables.

<h2 class="key-title">Add</h2>

<h2 class="key-entry">4D1EDE05-38C7-4A6A-9CC6-4BCCA8B38C14</h2>
<h3 class="key-entry">(APPLE_VENDOR_VARIABLE_GUID)</h3>
<br>

| Key | Type | Value | Description |
| --- | --- | --- | --- |
| DefaultBackgroundColor | Data | <> | Sets the background color for the boot.efi user interface in a BGRA color format, where each letter corresponds to a byte. Standard Mac colors are `BFBFBF00` for Light Gray and `00000000` for Syrah Black, but can be set to other colors as desired. |

<h2 class="key-entry">4D1FDA02-38C7-4A6A-9CC6-4BCCA8B30102</h2>
<h3 class="key-entry">(OC_VENDOR_VARIABLE_GUID)</h3>
<br>

| Key | Type | Value | Description |
| --- | --- | --- | --- |
| rtc-blacklist | Data | <> | Stores a list of memory addresses used by the AppleRtcRam quirk under ProtocolOverrides in the UEFI section of config.plist. This should be ignored by most users. |


<h2 class="key-entry">7C436110-AB2A-4BBB-A880-FE41995C9F82</h2>
<h3 class="key-entry">(APPLE_BOOT_VARIABLE_GUID)</h3>
<br>

| Key | Type | Value |
| --- | --- | --- |
| ForceDisplayRotationInEFI | Number | 0 |
| SystemAudioVolume | Data | <46> |

``ForceDisplayRotationInEFI`` can be used to set display rotation in the EFI graphics output mode used by OpenCore and early macOS boot. Useful for non-standard displays that may show wrong rotation by default, or for users with more custom setups such as vertical main displays. Takes one of the following rotation values: `0`, `90`, `180` and `270`, which corresponds to the image rotation in degrees.

``SystemAudioVolume`` sets the system volume while in UEFI firmware mode, including in the OpenCore boot picker. Most users can leave this alone. For specific configuration of this value, refer to Configuration.pdf.

<br>

| Key | Type | Value |
| ----- | ----- | ----- |
| boot-args | String | -v keepsyms=1 |

This important key stores the boot arguments used by macOS and is where you will add any necessary boot arguments for your system.
Commonly used ones are listed below.

<hr>
<h3 class="key-entry">General Boot Args</h3>

| boot-arg | Description | 
| ----- | ----- |
| -v | This enables verbose mode, which shows all the behind-the-scenes text that scrolls by as you're booting instead of the Apple logo and progress bar. It's invaluable to any Hackintosher, as it gives you an inside look at the boot process, and can help you identify issues, problem kexts, etc. |
| keepsyms=1 | This is a companion setting to debug=0x100 that tells the OS to also print the symbols on a kernel panic. That can give some more helpful insight as to what's causing the panic itself. |
| debug=0x100 | This disables macOS's watchdog which helps prevents a reboot on a kernel panic. That way you can hopefully glean some useful info and follow the breadcrumbs to get past the issues. It can in very rare cases cause the boot to get stuck on a black screen just before loading the macOS desktop. |

<h3 class="key-entry">GPU Related Boot Args</h3>

{: .note }
The following boot-args are Lilu boot args! They require the kext to be in use.

| boot-arg | Description |
| ----- | ----- |
| -wegnoegpu | Disables all external/dedicated GPUs besides the iGPU. |
| -wegnoigpu | Disables any integrated GPU, iGPU, in the system. |

{: .note }
The following boot-args are WhateverGreen boot args! They require the kext to be in use.

| boot-arg | Description | 
| ----- | ----- |
| agdpmod=vit9696 | Disables board-id check, may be needed for when screen turns black after finishing booting. |
| agdpmod=pikera | Used for disabling board ID checks on some Navi GPUs (RX 5000 & 6000 series) to fix black screen issues. Don't use if you use NootRX. |
| radpg=15 | Fixes initialization for Radeon HD 7730/7750/7770, Radeon R7 250/R7 250X GPUs. |
| -raddvi | Fixes DVI connector-type for Radeon 290X, 370, etc. |
| -radvesa | Forces GPU into VESA mode(no GPU acceleration), useful for troubleshooting. |
| -igfxvesa | Forces Intel iGPU into VESA mode. |

{: .note }
The following boot-args are Apple boot flags and will work without WhateverGreen/WEG.

| boot-arg | Description | 
| ----- | ----- |
| nv_disable=1 | Forces GPU into VESA mode. |
| -amd_no_dgpu_accel | Forces GPU into VESA mode. |

<hr>
<b>Continuing APPLE_BOOT_VARIABLE_GUID...</b>
<br>

| Key | Type | Value |
| --- | --- | --- |
| csr-active-config | Data | <00000000> |
| prev-lang:kbd | Data | <> |
| run-efi-updater | String | No |

``csr-active-config`` controls the current level of System Integrity Protection, SIP. As SIP has granular control over protecting various parts of the system, its current setting is stored as a 32-bit bitmask. The meaning of each bit in the bitmask is defined in the XNU source at [csr.h](https://raw.githubusercontent.com/apple-oss-distributions/xnu/main/bsd/sys/csr.h). Below is a list of common choices.

//TODO

| Data Value | Result | Description |
| --- | --- | --- |
| Placeholder | Placeholder | Placeholder |

``prev-lang:kbd`` should be removed from this GUID to force the use of a language picker in the recovery environment.

It can however be set as either type Data or type String. When set to String, it should be filled out with a language and country code, plus the desired keyboard layout in the format of language code-country code:layout number `lc-CC:123`. Some examples are:

| String | Description|
| --- | --- |
| `en-US:0` | US English with US standard keyboard. |
| `en-US:15000` | US English with US Int'l keyboard layout. |
| `sv-SE:7` | Sweden Swedish with Swedish Pro keyboard layout. |
| `ru-RU:252`| Russia Russian with a macOS "ABC" layout. |
| `pt-BR:128` | Brazil Portuguese with a macOS Brazilian keyboard layout. |

Short forms such as `ru:252`, `sv:7`, or `en:0` are also possible, where the first two letters are a language code, and the number is the keyboard layout code.

When set as type Data, you take your language, country code and keyboard layout combination and convert it from ASCII to hexadecimal and enter that in.

A list of keyboard layout codes will be added in the future.

``run-efi-updater`` controls if macOS firmware updaters are allowed to run during boot. As you are not on a real Mac, set this to the word `No` or some other value that can be interpreted as False such as `0` to prevent these updaters from running.

<h2 class="key-title">Delete</h2>

This section is used to tell OpenCore to delete variables from NVRAM, using their GUID and key. This is used because OpenCore won't overwrite or replace variables in NVRAM if they are already present, so this allows you to tell OpenCore to remove them so they can be replaced with new variables with new values.
For example, if you have undesired boot-args you cannot change, it would be because the GUID and key for boot-args is missing from here.

Other uses could be to remove the prev-lang:kbd variable to allow you to put a new one in, in case you have the wrong language in recovery.

<h2 class="key-title">LegacyOverwrite</h2>

Permits OpenCore to use an nvram.plist file to overwrite firmware variables. Only those firmware variables that would be accessible to an operating system can be overwritten.

<h2 class="key-title">LegacySchema</h2>

Relevant when the OpenCore driver OpenVariableRuntimeDxe.efi is in use, this sets what variables to load from an nvram.plist file. As this file is stored in the EFI partition, it is not secure and can be used to circumvent system security if certain variables such as `boot-args` and `csr-active-config` are included here.

The Sample.plist you copied will have a number of permitted variables already. These can be removed or left as-is.

<h2 class="key-title">WriteFlash</h2>
Should be set True.
This setting is what allows OpenCore to attempt to write all variables to the motherboard's NVRAM, which is often a type of non-volatile flash memory.
On systems with broken NVRAM this should be disabled.

<h2 align="center">
  <br>
  <div class="navigation-container">
    <a class="nav-button" href="../06-Misc/">&larr; Back Page</a>
    <a class="nav-button" href="../08-PlatformInfo/">Next Page &rarr;</a>
  </div>
  <br>
</h2>
