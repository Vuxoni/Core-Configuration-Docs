---
layout: default
title: EFI Setup
parent: Gathering Files
description: 
nav_order: 1
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
  <img width="650" height="200" src="../../../../assets/Headers/Header-EFISetup.png">
</p>

<h2 align="center">How to prepare OpenCore folder contents.</h2>
<br>

We'll be going over the folders that exist on your newly created OpenCore USB.

## **ACPI**

At least in the sense of the way we interact with it via OpenCore - acts as a bit of a go-between for the hardware and OS.  Windows and Linux have always had to deal with all sorts of vendors/OEMs doing all sorts of nonsense in their firmware - but since OS X / macOS has only (officially) needed to work with Apple firmware, Apple has been able to tailor much of the OS to expect certain things to be, *or not be*, there - or work in specific ways.  The ACPI folder allows us to provide supplemental SSDTs or even a patched DSDT in order to help coerce those OEM firmware tables into something that better suits OS X / macOS's expectations.

We'll talk more about ACPI and more specifically, how to figure out what you'll need initially (even write SSDTs) and when you run into issues with your firmware on OS X / macOS. **As of the initial OpenCore installation, the ACPI folder will be empty. Do not worry. You can continue reading**.

<hr>

## **Drivers**

This folder is used for storing supplemental UEFI drivers for your hardware's firmware to load. As previously explained, standard PC firmware (BIOS) lacks the ability to see/read/boot HFS+ / APFS disks or volumes. This folder is typically used to add either ``OpenHfsPlus.efi`` or ``HfsPlus.efi``. Other drivers can be loaded here for legacy hardware and the likes. **As of the initial OpenCore installation, you will see the collection of Drivers that OpenCorePkg ships with. This folder will not be empty.**

A list of all included drivers and their purpose will be found later. For now, we simply want to acknowledge the fact that OpenCore comes bundled with lots of drivers but we will not be using the majority of these and will likely end up deleting all of them except 2-3 drivers, later during the appropriate page. 

<hr>

## **Kexts**

Kernel Extensions are typically developed by Apple and can be found on OS X / macOS systems under ``/System/Library/Extensions``. These extend the functionality of the Kernel by adding support for various hardware and software. In the context of OpenCore and its own ``Kexts`` folder, we use the following to include third-party kexts that are developed by the community to further extend the support of the Kernel to work on non-Apple hardware.

Examples of this can be ``VirtualSMC.kext`` which makes it so that a standard PC which does not come with an SMC device that contains Apple's DSMOS (Don't Steal Mac OS X) passphrase or key can emulate an SMC Chip and satisfy the requirements. Other examples can be ``Itlwm.kext`` which are used to add support for unsupported Intel Wi-Fi cards. **As of the initial OpenCore installation, the Kexts folder will be empty. Do not worry. You can continue reading.** You will learn what would be required from your system later on.

<hr>

## **Tools**

OpenCore has a neat feature that lets you make use of various other UEFI "executables" or "binaries" as we mentioned earlier. This allows you to chain-load things like ``OpenShell.efi`` to view the current state of the machine under OpenCore. **As of the initial OpenCore installation, the Tools folder will contain bundled Tools. Do not worry. You can continue reading.** We simply want to understand that this section will require clean up later, as we will not be making use of any of these tools provided to us by OpenCorePkg. There are moments when a Helper may ask you to boot into ``OpenShell.efi``, and this is how you could achieve this.

<hr>

## **Resources**

As the name indicates, this folder holds resources for OpenCore to use for various beauty treatments. There comes a time much later in your hobby knowledge that you end up wanting to do things like making OpenCore more nice to look at. For this reason, this folder was mentioned last, as it really has the least importance and is NOT required to have a functional system. Other potential use-cases for this would be essentially getting something like the Mac startup Boot Chime that you hear ``Bong!`` on real Mac machines. **As of the initial OpenCore installation, the Resources folder will be empty. Do not worry. You can continue reading.**

<hr>

Now that you are aware of all of the folders and their purpose, you can now begin configuring the contents of each. The reason why we want to go through each folder first, is due to the fact that our first step during Configuration of the property list for OpenCore will be taking all the contents of the USB and essentially explaining to OpenCore what has what, and where is what. You can't continue until each folder is appropriately filled out and has contents required for your system.  

<h2 align="center">
  <br>
  <div class="navigation-container">
    <a class="nav-button" href="../../index">&larr; Back Page</a>
    <a class="nav-button" href="../01-ACPI/index">Next Page &rarr;</a>
  </div>
  <br>
</h2>
