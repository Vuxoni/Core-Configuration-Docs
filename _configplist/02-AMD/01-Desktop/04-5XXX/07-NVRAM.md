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

The variables below are listed by their GUID, the name of the GUID (not stored in NVRAM or in config.plist), its keys, and their values.

<h2 class="key-title">Add</h2>

<h2 class="key-entry">4D1EDE05-38C7-4A6A-9CC6-4BCCA8B38C14</h2>
<h3 class="key-entry">APPLE_VENDOR_VARIABLE_GUID</h3>

<br>

Placeholder text explaining this Key.

| Key | Type | Value |
| --- | --- | --- |
| DefaultBackgroundColor | Data | <> |

Placeholder information about other information that can be in this key.

<h2 class="key-entry">4D1FDA02-38C7-4A6A-9CC6-4BCCA8B30102</h2>
<h3 class="key-entry">OC_VENDOR_VARIABLE_GUID</h3>
<br, where the first two letters are a language code, and the number is the keyboard layout code.

Stores a list of memory addresses used by the AppleRtcRam quirk under ProtocolOverrides in the UEFI section of config.plist. This should be ignored by most users.

| Key | Type | Value |
| --- | --- | --- |
| rtc-blacklist | Data | <> |


<h2 class="key-entry">7C436110-AB2A-4BBB-A880-FE41995C9F82</h2>
<h3 class="key-entry">APPLE_BOOT_VARIABLE_GUID</h3>
<br>

Placeholder text explaining this Key. We go to explaining the other children first.

| Key | Type | Value |
| --- | --- | --- |
| ForceDisplayRotationInEFI | Number | 0 |
| SystemAudioVolume | Data | <46> |

``ForceDisplayRotationInEFI`` can be used to set display rotation in the EFI graphics output mode used by OpenCore and early macOS boot. Useful for non-standard displays that may show wrong rotation by default, or for users with more custom setups such as vertical main displays.
Takes one of the following rotation values: `0`, `90`, `180` and `270`, which corresponds to the image rotation in degrees.

``SystemAudioVolume`` sets the system volume while in UEFI firmware mode, including in the OpenCore boot picker. Most users can leave this alone.
For specific configuration of this value, refer to Configuration.pdf.

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

``csr-active-config`` is the 32-bit System Integrity Protection bitmask. Declared in XNU source code in [csr.h](https://raw.githubusercontent.com/apple-oss-distributions/xnu/main/bsd/sys/csr.h). Below is a list of common choices.

| Data Value | Result | Description |
| --- | --- | --- |
| Placeholder | Placeholder | Placeholder |

``prev-lang:kbd`` can be set as either type Data or type String. When set to String, it should be filled out with a language and country code, plus the desired keyboard layout in the format of language code-country code:layout code `lc-CC:123`. Some examples are:

`en-US:0` - US English with US standard keyboard.
`en-US:15000` - US English with US Int'l keyboard layout.
`sv-SE:7` - Sweden Swedish with Swedish Pro keyboard layout.
`ru-RU:252`- Russia Russian with a macOS "ABC" layout.
`pt-BR:128` - Brazil Portuguese with a macOS Brazilian keyboard layout.

Short forms such as `ru:252`, `sv:7`, or `en:0` are also possible, where the first two letters are a language code, and the number is the keyboard layout code.

When set as type Data, you take your language, country code and keyboard layout combination and convert it from ASCII to hexadecimal and enter that in.

A list of keyboard layout codes will be added in the future.

``run-efi-updater`` overrides EFI firmware updating support in macOS (MultiUpdater, ThorUtil, and so on). Setting this to No or alternative boolean-castable value will prevent any firmware updates in macOS starting with 10.10 at least.

<h2 class="key-title">Delete</h2>

Forcibly rewrites NVRAM variables, do note that Add will not overwrite values already present in NVRAM so values like boot-args should be left alone. This section mirrors the Add section, but allows you to sanity check NVRAM variables are being updated.

<h2 class="key-title">LegacyOverwrite</h2>

Permits overwriting firmware variables from nvram.plist.

<h2 class="key-title">LegacySchema</h2>

Used for assigning NVRAM variables, used with OpenVariableRuntimeDxe.efi. Only needed for systems without native NVRAM. The values under this can be deleted safely.

<h2 align="center">
  <br>
  <div class="navigation-container">
    <a class="nav-button" href="../06-Misc/">&larr; Back Page</a>
    <a class="nav-button" href="../08-PlatformInfo/">Next Page &rarr;</a>
  </div>
  <br>
</h2>
