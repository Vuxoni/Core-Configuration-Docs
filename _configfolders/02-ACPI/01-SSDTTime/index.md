---
layout: default
title: SSDTTime
parent: ACPI
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

  .windows-next-button-container {
    text-align: right;
  }

  .windows-next-button {
    margin: 10px;
    top: 0px;
    bottom: 0px;
    left: 0px;
    right: 0px;
  }
</style>

<p align="center">
  <img width="650" height="200" src="../../../../assets/Header-Tools-SSDTTime.png">
</p>

The following section explains how you can generate your SSDTs. That should save us a ton of time. To do this, we use another tool from [CorpNewt](https://github.com/corpnewt), SSDTTime[https://github.com/corpnewt/SSDTTime].

## How do I use SSDTTime?

First of all, we want to get the tool by downloading the entire main branch of the repository or cloning the repository as is. 

<div style="text-align: center;" markdown="1">
  [![SSDTTimeRepository](/assets/SSDTTime/SSDTTimeRepo.png)](/assets/SSDTTime/SSDTTimeRepo.png)
</div>

 As before, we have various scripts to select from, depending on our operating system. Choose the appropriate script for your OS.

<div style="text-align: center;" markdown="1">
  [![SSDTTimeFiles](/assets/SSDTTime/SSDTTimeFiles.png)](/assets/SSDTTime/SSDTTimeFiles.png)
</div>

Now we are able to open the program. Upon launching it, we are greeted with an interface that should look similar to the screenshot below. The program provides us with various options, that allow us to create SSDTs right away. 

<div style="text-align: center;" markdown="1">
  [![SSDTTimeBlank](/assets/SSDTTime/SSDTTimeLoadedTables.png)](/assets/SSDTTime/SSDTTimeLoadedtables.png)
</div>

In order to create SSDTs, SSDTTime requires us to provide ACPI tables found in our firmware. In the screenshot above, SSDTTime loaded all of our tables correctly.
Normally, the program should read them automatically from the computer on which you're using the script on. However, if this doesn't work or if you want to create SSDTs for another system, you'll need to add the tables manually. If SSDTTime loads the correct tables, you can skip this step.

## Dumping ACPI tables

In order to dump our tables, we need a few things. First of all, we want to grab an [UEFI shell](https://github.com/tianocore/edk2/blob/edk2-stable201903/ShellBinPkg/UefiShell/X64/Shell.efi). Then, we want to grap [ACPIDump.efi](https://github.com/dortania/OpenCore-Install-Guide/blob/master/extra-files/acpidump.efi.zip), that will allow us to dump our ACPI tables.

Now we need a USB stick. This stick must be formatted to ```FAT32``` - the size doesn't matter. We want to create a folder called ```EFI``` in the root directory of the stick. Then, create a subfolder called ```BOOT```. In this subfolder, we paste ```Shell.efi``` and rename it to ```Bootx64.efi```. We then also paste ACPIDump.efi - this file doesn't have to be renamed. As a result, our stick should have the following structure:

<div style="text-align: center;" markdown="1">
  [![ACPIDump stick structure](/assets/SSDTTime/ACPIStick.png)](/assets/SSDTTime/ACPIStick.png)
</div>

{: .note }
Bootx64.efi is not the same file as the one provided inside OpenCorePkg! Do NOT confuse them. 


We then boot this stick. In the terminal that we then see, we enter "```ACPIDump.efi -b -n```". This should create a bunch of files inside the root directory of the stick. We can now access the files from our stick. After we've dumped our tables, we wont need the stick anymore. However, make sure that you saved the tables somewhere.

<div style="text-align: center;" markdown="1">
  [![ACPIDump](/assets/SSDTTime/ACPIDump.png)](/assets/SSDTTime/ACPIDump.png)
</div>

Fortunately, SSDTTime is able to process .dat tables. So we don't need to rename the tables. If you still need .aml tables, you can simply rename the files; converting them is not necessary. We can simply select a folder containing our tables in SSDT using option ```D. Select ACPI table or folder containing tables```.

## SSDTTime's options

{: .note }
Below you will find a list of all SSDTTime options. However, that does NOT mean you should select every one! To find out which option to choose, please see the corresponding Gathering files section.

- *1.* **FixHPET**
Using the FixHPET option will create ```SSDT-HPET```. ```SSDT-HPET``` re-defines the HPET's _CRS method to claim IRQs (Individual Interupt Requests) that macOS expects the device to be assigned to it.  It requires several ACPI patches to remove conflicting IRQs from other devices, as well as renaming the HPET's _CRS method to XCRS in order to re-define it.
Creating ```SSDT-HPET``` will also create several ACPI patches that we can find in the also generated ```patches_OC.plist```. ```SSDT-HPET``` will be useless if you dont merge them into your ```config.plist```.

SSDTTime will show us conflicting IRQs:

<div style="text-align: center;" markdown="1">
  [![HPET](/assets/SSDTTime/SSDTTimeHPET.png)](/assets/SSDTTime/SSDTTimHPET.png)
</div>

We can now choose the default option ```C. Only Conflicting IRQs from Legacy Devices``` to resolve the existing conflicts.

- *2.* **FakeEC**
Using the FakeEC option will generate SSDT-EC. macOS is very picky about having an EC (Embedded Controller) inside ACPI tables. If you have a ```PNP0C09```  (the HID for embedded controller) device defined in your ACPI, macOS will stall on some versions. In addition, Desktop ECs are not compatible with macOS - renaming them is therefore not a solution. Further, ```AppleBusPowerController``` requires a device named "EC" to be present (while it doesn't have to be a ```PNP0C09``` device). 
SSDT-EC does two things:
1. It returns 0 for any ```PNP0C09``` devices ```_STA``` (status) method to disable it - it prevents macOS from using the incompatible EC.
2. It creates a new device named "EC" without a ```PNP0C09``` HID to satisfy AppleBusPowerController.

- *3.* **Laptop EC**
Laptop EC leaves the built-in EC untouched - it is what manages battery statistics, brightness notifications, hotkeys, etc. on laptops. If there isn't a device called "EC", Laptop EC creates a fake one. However, if there is already a ```PNP0C09 device``` called "EC", Laptop EC won't create a SSDT as it's doesn't needed.

- *4.* **USBX**
Starting with Skylake, systems started to change the way they handle USB devices. Consequently, USBX defines USB power properties - it defines a top-level USBX device. When a high-powered USB device is plugged in, the operating system gets informed of the appropriate power level to provide. SSDT-USBX is only needed on SMBIOS (System Management BIOS) based on Skylake and newer.

SSDTTime is going to show us our USBX device properties:

<div style="text-align: center;" markdown="1">
  [![USBX](/assets/SSDTTime/SSDTTimeUSBX.png)](/assets/SSDTTime/SSDTTimeUSBX.png)
</div>

In almost every case, we can use the default option ```B. Build SSDT-USBX```.

- *5.* **PluginType**
- *6.* **PMC**
- *7.* **RTCAWAC**
- *8.* **USB Reset**
- *9.* **PCI Bridge**
- *0.* **PNLF**
- *A.* **XOSI**
- *B.* **Fix DMAR**

<h2 align="center">
  <br>
  <div class="windows-next-button-container">
  <a class="windows-next-button" href="../01-Windows/">Windows &rarr;</a>
  </div>
  <div class="navigation-container">
    <a class="nav-button" href="../../index/">&larr; Back Page</a>
    <a class="nav-button" href="../02-Linux/">Linux &rarr;</a>
  </div>
  <br>
</h2>
