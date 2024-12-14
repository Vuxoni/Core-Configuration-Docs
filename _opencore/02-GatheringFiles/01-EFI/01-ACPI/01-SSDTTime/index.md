---
layout: default
title: SSDTTime
parent: ACPI
grand_parent: EFI Setup
nav_order: 1
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

  .top-button {
    margin: 10px;
    align: center;
  }
</style>

<p align="center">
  <img width="650" height="200" src="../../../../../../assets/Headers/Header-Tools-SSDTTime.png">
</p>

The following section explains how you can generate your SSDTs using another tool from [CorpNewt](https://github.com/corpnewt), named [SSDTTime](https://github.com/corpnewt/SSDTTime).

## **How do I get SSDTTime?**

First of all, we want to get the tool by downloading the entire main branch of the repository or cloning the repository as is. 

<div style="text-align: center;" markdown="1">
  [![SSDTTimeRepository](/assets/SSDTTime/SSDTTimeRepo.png)](/assets/SSDTTime/SSDTTimeRepo.png)
</div>

As before, we have various scripts to select from, depending on our operating system. Choose the appropriate script for your OS.

<div style="text-align: center;" markdown="1">
  [![SSDTTimeFiles](/assets/SSDTTime/SSDTTimeFiles.png)](/assets/SSDTTime/SSDTTimeFiles.png)
</div>

Now we are able to open the program. Upon launching it, we are greeted with an interface that should look similar to the screenshot below. The program provides us with various options and may not be exact to the image below if changes are made to SSDTTime. 

<div style="text-align: center;" markdown="1">
  [![SSDTTime initial Windows launch](/assets/SSDTTime/)](/assets/SSDTTime/)
</div>

In order to create SSDTs, SSDTTime requires us to provide ACPI tables found in our firmware, for it to create the final resulting .aml files.

<div style="text-align: center;" markdown="1">
  [![Output from pressing the "P. Dump the current system's ACPI tables"](/assets/SSDTTime/)](/assets/SSDTTime/)
</div>

Selecting the option named ``Dump the current system's ACPI tables``, you will automatically have SSDTTime attempt to dump the current machines ACPI/DSDT. Afterwards, it should now be loaded and you can begin generating specific SSDT's for your system.

From the descriptions below, you will be able to determine what options you will require to boot your system, according to your previous look into your hardware's support and requirements.

The rest of this page documents all SSDTTime options and their purpose for safe keeping. There is a "Return to Top" button at the bottom. Please scroll through and read this page to continue.

<h2 align="center">
  <br>
  <div class="navigation-container">
    <a class="nav-button" href="../../index">&larr; Back Page</a>
    <a class="nav-button" href="../../../02-Drivers/">Next Page &rarr;</a>
  </div>
  <br>
</h2>

<hr>

{: .warning }
You must NOT select every option! To figure out which options to choose and which SSDTs to generate, please see the corresponding page from [Gathering files]().

## **SSDTTime's Options**

## **FixHPET**

Using the FixHPET option will create ``SSDT-HPET``. It re-defines the HPET's _CRS method to claim IRQs (Individual Interupt Requests) that macOS expects the device to be assigned to it. It requires several ACPI patches to remove conflicting IRQs from other devices, as well as renaming the HPET's _CRS method to XCRS in order to re-define it.

Creating ``SSDT-HPET`` will also create several ACPI patches that we can find in the also generated ``patches_OC.plist``.

``SSDT-HPET`` will be useless if you do not merge them into your ``config.plist``.

SSDTTime will show us conflicting IRQs:

<div style="text-align: center;" markdown="1">
  [![HPET](/assets/SSDTTime/SSDTTimeHPET.png)](/assets/SSDTTime/SSDTTimHPET.png)
</div>

We can now choose the default option ```C. Only Conflicting IRQs from Legacy Devices``` to resolve the existing conflicts.

<hr>

## **FakeEC**

Using the FakeEC option will generate ``SSDT-EC.aml``.

macOS is very picky about having an EC (Embedded Controller) inside ACPI tables. If you have a ```PNP0C09```  (the HID for embedded controller) device defined in your ACPI, macOS will stall on some versions.

In addition, Desktop ECs are not compatible with macOS - renaming them is therefore not a solution. Further, ```AppleBusPowerController``` requires a device named "EC" to be present (though it does not have to be a ```PNP0C09``` device).

SSDT-EC does two things:

1. It returns 0 for any ```PNP0C09``` devices ```_STA``` (status) method to disable it - it prevents macOS from using the incompatible EC.
2. It creates a new device named "EC" without a ```PNP0C09``` HID to satisfy AppleBusPowerController.

<hr>

## **Laptop EC**

Laptop EC leaves the built-in EC untouched - it is what manages battery statistics, brightness notifications, hotkeys, etc. on laptops. If there isn't a device called "EC", Laptop EC creates a fake one. However, if there is already a ```PNP0C09 device``` called "EC", Laptop EC won't create an SSDT as it's not needed.

<hr>

## **USBX**

Starting with Skylake, systems started to change the way they handle USB devices. Consequently, USBX defines USB power properties - it defines a top-level USBX device.

When a high-powered USB device is plugged in, the operating system gets informed of the appropriate power level to provide.

SSDT-USBX is only needed on SMBIOS (System Management BIOS) based on Skylake and newer.

SSDTTime is going to show us our USBX device properties:

<div style="text-align: center;" markdown="1">
  [![USBX](/assets/SSDTTime/SSDTTimeUSBX.png)](/assets/SSDTTime/SSDTTimeUSBX.png)
</div>

In almost every case, we can use the default option ```B. Build SSDT-USBX```.

<hr>

## **PluginType**

Using PluginType will either create SSDT-PLUG or SSDT-PLUG-ALT.

Both SSDTs will inject ```PluginType = 1``` into the first CPU processor object.

Some newer CPUs define their CPU cores/threads differently, therefore its needed to redefine them using SSDT-PLUG-ALT. It redefines existing ```ACPI0007``` devices as legacy ```Processor ()``` objects so macOS is able to recognize them. SSDTTime automatically takes care of generating either SSDT-PLUG or SSDT-PLUG-ALT, according to your systems requirements.

<hr>

## **PMC**

{: .note}
Z370 does not require SSDT-PMC as its actually a [rebranded 200-series chipset](https://www.pcbuildersclub.com/en/2019/01/der8auer-proves-that-intels-lga-1151v2-z370-and-z390-are-pointless/amp/).

Intel-300-series mainboards lack definitions for PMC/PPMC devices responsible for managing native NVRAM. Most likely Intel simply forgot about them.

Apple defined a device called ```APP9876``` to access it with its AppleIntelPCHPMC driver. SSDT-PMC therefore defines such a device and disables it in every other OS than macOS.

Without SSDT-PMC, NVRAM writes are not possible.

<hr>

## **RTCAWAC**

An AWAC (Alternate Wake-up and Clock) on a mainboard refers to a system clock configuration found on newer Intel motherboards.

It is designed to replace the traditional Real-Time Clock (RTC) used in older systems. RTCAWAC disables the AWAC, enables or simulates the RTC, and checks and adjusts the RTC ranges as needed.

<hr>

## **USB Reset**

{: .internalnote }
This information is to be filled out.

<hr>

## **PCI Bridge**

{: .internalnote }
This information is to be filled out.

<hr>

## **PNLF**

{: .internalnote }
This information is to be filled out.

<hr>

## **XOSI**

{: .internalnote }
This information is to be filled out.

<hr>

## **Fix DMAR**

{: .internalnote }
This information is to be filled out.

<hr>

## **Dumping ACPI tables for a secondary machine**

If you need to generate SSDTs for a secondary machine, you must still dump the ACPI Tables from said secondary machine to select them in SSDTTime.

In order to dump our tables, we need a few things. First of all, we want to grab [UEFI shell](https://github.com/tianocore/edk2/blob/edk2-stable201903/ShellBinPkg/UefiShell/X64/Shell.efi). Then, we want to grab [ACPIDump.efi](https://github.com/dortania/OpenCore-Install-Guide/blob/master/extra-files/acpidump.efi.zip), that will allow us to dump our ACPI tables.

Now we need a USB stick. This stick must be formatted to ```FAT32``` - the size doesn't matter. We want to create a folder called ```EFI``` in the root directory of the stick. Then, create a subfolder called ```BOOT```. In this subfolder, we paste ```Shell.efi``` and rename it to ```Bootx64.efi```. We then also paste ACPIDump.efi - this file doesn't have to be renamed. As a result, our stick should have the following structure:

<div style="text-align: center;" markdown="1">
  [![ACPIDump stick structure](/assets/SSDTTime/ACPIStick.png)](/assets/SSDTTime/ACPIStick.png)
</div>

{: .note }
Bootx64.efi is not the same file as the one provided inside OpenCorePkg! Do NOT confuse them. An EFI is simply a bootable UEFI executable, and this is how to quickly prepare a USB with the UEFI Shell and ACPIDump.efi binary program to execute in the Shell environment.

We then need to reboot to boot this stick. You are dropped into the UEFI Shell, we must enter:

```bash
ACPIDump.efi -b -n
```

This should create a bunch of files inside the root directory of the stick that we can now access for SSDTTime. 

After we've dumped our tables, we wont need the stick anymore. However, make sure that you saved the tables somewhere.

<div style="text-align: center;" markdown="1">
  [![ACPIDump](/assets/SSDTTime/ACPIDump.png)](/assets/SSDTTime/ACPIDump.png)
</div>

## Configuring SSDTTime for dump usage

Fortunately, SSDTTime is able to process .dat tables. So we don't need to rename the tables.

If you still need .aml tables, you can simply rename the files; converting them is not necessary.

We can simply select a folder containing our tables in SSDTTime by using option labelled ``Select ACPI table or folder containing tables``.

<div style="text-align: center;" markdown="1">
  [![SSDTTime Selection of Dump](/assets/SSDTTime/)](/assets/SSDTTime/)
</div>

<h2 align="center">
  <br>
  <div>
    <a class="top-button" href="#">&uarr; Go to the Top &uarr;</a>
  </div>
  <br>
</h2>
