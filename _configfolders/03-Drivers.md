---
layout: default
title: Drivers
nav_order: 3
has_children: false
has_toc: false
---

<style>
  .next-button-container {
      text-align: right;
    }

  .next-button {
      top: 0px;
      bottom: 0px;
      left: 0px;
      right: 0px;
  }
</style>

<p align="center">
  <img width="650" height="200" src="../../../assets/Header-OpenCore-Drivers.png">
</p>

<h2 align="center">Placeholder Information</h2>

<h4 align="center">This page is a stub, but this page should:</h4>
<br>

1. List known drivers and chart them, as well as advising which are required, and which can be deleted

2. Note what, hopefully, all drivers do, even if they're not needed; Having the information in a central page will be useful for those who want to think for themselves.

Add general informations about .efi files (and other drivers), explain dxe drivers

## Drivers included in OpenCorePkg

| Driver                 | What does it do?                                                      | Do I need it?                                                                                                                         | Notes                                                        |
| ---------------------- | --------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------ |
| ArpDxe                 | Networking protocol driver                                           | ❌                                                                                                                                    | Part of EDKII                                                |
| AudioDxe               | Setting up a boot chime                                               | Don't add this for initial installation. Purely optional, come back to this in the post installation process.                         |                                                              |
| BiosVideo              | Basic video driver for pre-UEFI systems                               | ❌                                                                                                                                    | This driver does not give you graphic acceleration in macOS! |
| CrScreenshotDxe        | Tool to make screenshots                                              | ❌                                                                                                                                    |                                                              |
| Dhpc4Dxe               | Networking protocol driver                                           | ❌                                                                                                                                    |                                                              |
| DnsDxe                 | Networking protocol driver                                           | ❌                                                                                                                                    |                                                              |
| DpcDxe                 | Networking protocol driver                                           | ❌                                                                                                                                    |                                                              |
| Ext4Dxe                | ?                                                                     |                                                                                                                                       |                                                              |
| FirmwaresettingsEntry  | Used to boot UEFI (aka BIOS) settings through OpenCore's boot menu                                                                     | ❌                                                                                                                                    |                                                              |
| HiiDatabase            | Used to fix graphic issues on pre-UEFI systems                        | Don't add this for initial installation.                                                                                              | This driver does not give you graphic acceleration in macOS! |
| HttpBootDxe            |                                                                       | ❌                                                                                                                                    |                                                              |
| HttpDxe                |                                                                       | ❌                                                                                                                                    |                                                              |
| HttpUtilitiesDxe       |                                                                       | ❌                                                                                                                                    |                                                              |
| Ip4Dxe                 |                                                                       | ❌                                                                                                                                    |                                                              |
| MnpDxe                 |                                                                       | ❌                                                                                                                                    |                                                              |
| NvmExpressDxe          |                                                                       | ❌                                                                                                                                    |                                                              |
| OpenCanopy             | GUI driver for OpenCore                                               | Don't add this for initial installation unless you know what you are doing                                                            |                                                              |
| OpenHfsPlus            | Open source HFS+ driver for macOS                                     | Much slower than HFSPlus, so you shouldn't use it (unless you know what you're doing). Don't use on systems that lack RDRAND support. |                                                              |
| OpenLegacyBoot         | Used to boot legacy OS from pre-UEFI systems                          |                                                                                                                                       |                                                              |
| OpenLinuxBoot          | Used to allow dual-booting Linux through OpenCore                                                                      | Don't add this for intial installation unless you want to boot Linux through OpenCore                                                                                                                                      |                                                              |
| OpenNtfsDxe            | Driver to read NTFS                                                   | (ToDo: When tf did Apple start to include NTFS support, find out when to add this driver)                                             |                                                              |
| OpenPartitionDxe       |                                                                       |                                                                                                                                       |                                                              |
| OpenRuntime            | Required for fixing NVRAM, power management, RTC, memory mapping etc. | ✅                                                                                                                                    |                                                              |
| OpenUsbKbDxe           | Used for fixing USB keyboard on legacy BIOS systems                                                                      | Don't add this if your machine supports UEFI                                                                                                                                      |                                                              |
| OpenVariableRuntimeDxe | Emulating NVRAM                                                                      | Don't add this unless your hardware NVRAM isn't working on macOS                                                                                                                                      |                                                              |
| Ps2KeyboardDxe         |                                                                       |                                                                                                                                       |                                                              |
| Ps2MouseDxe            |                                                                       |                                                                                                                                       |                                                              |
| ResetNvramEntry        | Required to reset the system’s NVRAM                                  | ✅                                                                                                                                    |                                                              |
| SnpDxe                 |                                                                       | ❌                                                                                                                                    |                                                              |
| TcpDxe                 |                                                                       | ❌                                                                                                                                    |                                                              |
| ToggleSipEntry         |                                                                       |                                                                                                                                       |                                                              |
| Udp4Dxe                |                                                                       | ❌                                                                                                                                    |                                                              |
| UsbMouseDxe            | Don't add this for initial installation, only used for enabling USB mouse on GUI interface provided by OpenCanopy (for legacy systems at least)                                                                      |                                                                                                                                       |                                                              |
| XhciDxe                | Don't add this unless your machine doesn't support UEFI and is for adding external USB 3 PCI cards support                                                                     |                                                                                                                                       |                                                              |

## Other drivers

| Driver         | What does it do?                                              | Do I need it?                                               | Notes                                                                         |
| -------------- | ------------------------------------------------------------- | ----------------------------------------------------------- | ----------------------------------------------------------------------------- |
| btrfs_x64      | Driver for BTRFS filesystem                                                              | Only when you are dual-booting Linux on OpenCore which uses BTRFS                                                            |                                                                               |
| EnableGop      |                                                               |                                                             |                                                                               |
| ExFatDxe       |                                                               |                                                             |                                                                               |
| ext4_x64       | Driver for ext4 filesystem                                                              | Only when you are dual-booting Linux on OpenCore which uses ext4                                                            |                                                                               |
| HfsPlus        | Apple’s proprietary driver for HFS volumes, not included OOB. | Yes, but don't use it at the same time as other HFS drivers | Don't use it on systems that lack RDRAND support.                             |
| HfsPlusLegacy  | HFS+ driver for systems that lack RDRAND support.             | Yes, if you lack RDRAND support                             |                                                                               |
| HfsPlus32      | HfsPlus driver for 32-bit CPUs.                               | Yes, if you have a 32-bit CPU                               | Do not use it on 64-bit systems (unless you are specifically asked to do so). |
| EnhancedFatDxe |                                                               |                                                             |                                                                               |


<h2 align="center">
  <br>
  <div class="next-button-container">
  <a class="next-button" href="../04-Kexts">Next Page &rarr;</a>
  </div>
  <br>
</h2>
