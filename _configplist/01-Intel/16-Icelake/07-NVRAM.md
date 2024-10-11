---
layout: default
title: NVRAM
parent: Icelake
grand_parent: Intel CPUs
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

<h2 class="key-title">Add</h2>

<h2 class="key-entry">APPLE_VENDOR_VARIABLE_GUID</h2>
<h3 class="key-entry">4D1EDE05-38C7-4A6A-9CC6-4BCCA8B38C14</h3>
<br>

Placeholder text explaining this Key.

| Key | Type | Value |
| --- | --- | --- |
| DefaultBackgroundColor | Data | <> |

Placeholder information about other information that can be in this key.

<h2 class="key-entry">OC_VENDOR_VARIABLE_GUID</h2>
<h3 class="key-entry">4D1FDA02-38C7-4A6A-9CC6-4BCCA8B30102</h3>
<br>

Placeholder text explaining this Key.

| Key | Type | Value |
| --- | --- | --- |
| rtc-blacklist | Data | <> |

Placeholder information about other information that can be in this key.

<h2 class="key-entry">APPLE_BOOT_VARIABLE_GUID</h2>
<h3 class="key-entry">7C436110-AB2A-4BBB-A880-FE41995C9F82</h3>
<br>

Placeholder text explaining this Key. We go to explaining the other children first.

| Key | Type | Value |
| --- | --- | --- |
| ForceDisplayRotationInEFI | Number | 0 |
| SystemAudioVolume | Data | <> |

``ForceDisplayRotationInEFI`` is a 32-bit integer defining display rotation. Can be 0 for no rotation or any of 90, 180, 270 for matching rotation in degrees.

``SystemAudioVolume`` is a data key that takes an 8-bit unsigned integer. The bit of 0x80 means muted. The remaining bits are used to encode the raw amplifier gain setting to be applied to the audio amplifier in use. Exactly what this value means depends on the codec (and potentially on the specific amplifier within the codec). This value is capped by macOS to the MaximumBootBeepVolume AppleHDA layout value, to avoid over-loud audio playback in the firmware.
<br>

| Key | Type | Value |
| ----- | ----- | ----- |
| boot-args | String | -v keepsyms=1 |

We can use this Key and it's value to modify boot-args. Use the chart below for various arguments required for this CPU. Includes extra information that may be useful later.

<hr>
<h3 class="key-entry">General Boot Args</h3>

| boot-arg | Description | 
| ----- | ----- |
| -v | This enables verbose mode, which shows all the behind-the-scenes text that scrolls by as you're booting instead of the Apple logo and progress bar. It's invaluable to any Hackintosher, as it gives you an inside look at the boot process, and can help you identify issues, problem kexts, etc. |
| keepsyms=1 | This is a companion setting to debug=0x100 that tells the OS to also print the symbols on a kernel panic. That can give some more helpful insight as to what's causing the panic itself. |
| debug=0x100 | This disables macOS's watchdog which helps prevents a reboot on a kernel panic. That way you can hopefully glean some useful info and follow the breadcrumbs to get past the issues. |

<h3 class="key-entry">GPU Related Boot Args</h3>

{: .note }
The following boot-args are Lilu boot args! They require the kext to be in use.

| boot-arg | Description |
| ----- | ----- |
| -wegnoegpu | Disables all External/Dedicated GPUs besides the iGPU. |

{: .note }
The following boot-args are WhateverGreen boot args! They require the kext to be in use.

| boot-arg | Description | 
| ----- | ----- |
| agdpmod=vit9696 | Disables board-id check, may be needed for when screen turns black after finishing booting. |
| agdpmod=pikera | Used for disabling board ID checks on some Navi GPUs (RX 5000 & 6000 series). Don't use if you use NootRX. |
| radpg=15 | Fixes initialization for HD 7730/7750/7770/R7 250/R7 250X |
| -raddvi | Fixes DVI connector-type for 290X, 370, etc |
| -radvesa | Forces GPU into VESA mode(no GPU acceleration), useful for troubleshooting. |
| -igfxvesa | Forces Intel iGPU into VESA mode |

{: .note }
The following boot-args are Apple boot flags and will work without WEG.

| boot-arg | Description | 
| ----- | ----- |
| nv_disable=1 | Forces GPU into VESA mode. |
| -amd_no_dgpu_accel | Forces GPU into VESA mode. |

<hr>
<b>Continuing APPLE_BOOT_VARIABLE_GUID...</b>
<br>

| Key | Type | Value |
| --- | --- | --- |
| csr-active-config | Data | <> |
| prev-lang:kbd | Data | <> |
| run-efi-updater | String | No |

``csr-active-config`` is a 32-bit System Integrity Protection bitmask. Declared in XNU source code in [csr.h](https://raw.githubusercontent.com/apple-oss-distributions/xnu/main/bsd/sys/csr.h). Below is a chart of common choices.

| Data Value | Result | Description |
| --- | --- | --- |
| Placeholder | Placeholder | Placeholde |

``prev-lang:kbd`` takes a Data or an ASCII string defining default keyboard layout. Format is lang-COUNTRY:keyboard, e.g. ru-RU:252 for Russian locale and ABC keyboard. Also accepts short forms:
ru:252 or ru:0 (U.S. keyboard, compatible with 10.9). Using non-latin keyboard on 10.14 will not enable ABC keyboard, unlike previous and subsequent macOS versions, and is thus not recommended in case 10.14 is needed.

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
