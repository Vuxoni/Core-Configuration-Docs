---
layout: default
title: Gathering Files
description: This section goes over how to gather all the files required by OpenCore, and specifics for hardware.
nav_order: 2
has_children: true
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
</style>

<p align="center">
  <img width="650" height="200" src="../../../assets/Headers/Header-GatheringFiles.png">
</p>

<h2 align="center">Where to source OpenCore, Where to install it to.</h2>
<br>

# **Fetching OpenCorePkg**

To begin, you will want to go to the **[OpenCorePkg](https://github.com/acidanthera/OpenCorePkg)** Github page. On the right side, you will see a ``Releases`` tab. This will take you to the latest version that is available for download. We recommend downloading the ``DEBUG`` variant so you can get the best logs when requesting support.

The contents of the zip will contain roughly the following files:

```bash
├── Docs
│   ├── AcpiSamples
│   │   ├── Binaries
│   │   └── Source
│   ├── Changelog.md
│   ├── Configuration.pdf
│   ├── Differences.pdf
│   ├── Sample.plist
│   └── SampleCustom.plist
├── IA32
├── Utilities
└── X64
    └── EFI
        ├── BOOT
        │   └── BOOTx64.efi
        └── OC
            ├── ACPI
            ├── Drivers
            ├── Kexts
            ├── OpenCore.efi
            ├── Resources
            └── Tools
```

# **Preparing the USB Drive**

What you'll want to do, is begin by selecting the appropriate folder for your systems architecture. For this example, we will be using ``X64`` instead of ``IA32``.

Move the ``EFI`` folder within the architecture of choice, and drop it to the root of your recently freshly formatted USB drive.

<p align="center">
  <img width="100%" height="100%" src="../../../assets/GatheringFiles/RootOfUSBDrive-NoRecoveryOS.png">
</p>

Before we can continue, we must do an initial runthrough of the contents of ``USB/EFI/OC`` to not only clean it up, but actually configure each folder. When you are ready to continue, press below.

<h2 align="center">
  <br>
  <div class="navigation-container">
    <a class="nav-button" href="../../01-Introduction/">&larr; Back Page</a>
    <a class="nav-button" href="../01-EFI/index">Next Page &rarr;</a>
  </div>
  <br>
</h2>
