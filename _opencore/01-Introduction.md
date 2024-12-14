---
layout: default
title: Introduction
description: Placeholder
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
  <img width="650" height="200" src="../../../assets/Headers/Header-Introduction.png">
</p>

<h2 align="center">What is OpenCore? How can we use it?</h2>
<br>

 OpenCore is known as a custom bootloader that has the unique ability to see, and boot HFS+ and APFS disks and disk images (DMG). In the world of UEFI firmware, you can run what are essentially "binaries" or "executables". Popular bootloaders you're familiar with, like GRUB or the Windows Boot Manager are mini UEFI programs that load the intended OS.

OpenCore unlike other bootloaders, has to be manually configured to properly boot the Mac operating system. This is where you are able to use OpenCore to your advantage. Issues you are aware of, can be fixed with enough persistence and proper configuration.

As .efi files are simply bootable by most UEFI firmwares via a USB, we can use a flash drive to configure OpenCore until we are satisfied it is as complete as it can be. This allows us to quickly modify ``config.plist`` and reboot to quickly prototype these changes. Later, during Post Installation, when we are satisfied with our results of our EFI you can install it to the usual EFI partition that exists on your disk. This removes the necessity of using a USB to boot OS X / macOS.

<br>
To continue in this guide you will require:

- USB Flash Drive (2GB+)
- ~10GB Free Space on currently booted OS for downloading and preparing files.

<br>
Begin by formatting your USB to FAT32. When you are ready please continue. If you require assistance with formatting your USB flash drive to FAT32, scroll past the Navigation Bar.

<h2 align="center">
  <br>
  <div class="navigation-container">
    <a class="nav-button" href="../../hardware/04-CompatibilityCharts/05-Misc/index">&larr; Back Page</a>
    <a class="nav-button" href="../02-GatheringFiles/index">Next Page &rarr;</a>
  </div>
  <br>
</h2>

<hr>
<p align="center">
  <img width="650" height="200" src="../../../../assets/Headers/Header-UsingWindows.png">
</p>

<h2 align="center">Using Rufus</h2>
<br>

{: .note }
This program comes in two forms, an installation and a portable version. Be careful which you download, and pay attention to where you place it if it is the portable version. You can download [Rufus](https://rufus.ie/en/) by clicking its name.

<div align="center">
<a href=""><img src="../../../../assets/Rufus/ProductUI.png" alt=""></a>
</div>

<p align="center">Above is the window that will appear when launching Rufus.</p>

<p align="center">To format a large flash drive that cannot be formatted via the Windows UI in Windows Explorer, we can use Rufus which allows us to not only make bootable USBs but luckily, simply format large flash drives as FAT32. The first option is to select said USB. Ensure you are choosing the correect USB! This is a destructive tool, please be careful and pay attention to what you are about to format.</p>

<p align="center">We can set the <code>Boot selection</code> type to <code>Non bootable</code>.</p>

<p align="center">If your system supports booting GPT formatted disks, select GPT. Else, use MBR.</p>

<p align="center">For the format options, you can name your USB stick anything you'd like. For File System, we'll obviously want to select FAT32. Cluster Size can remain its default value. Most likely, you'll want to deselect <code>Create extended label and icon files</code> to keep the USB clean.</p>

<p align="center">Once you're ready to continue, format the USB and head to the next page.</p>

<h2 align="center">
  <br>
  <div>
    <a class="top-button" href="#">&uarr; Go to Top &uarr;</a>
  </div>
  <br>
</h2>

<hr>
<p align="center">
  <img width="650" height="200" src="../../../../assets/Headers/Header-UsingLinux.png">
</p>

<h2 align="center">Using Terminal</h2>
<br>

{: .note }
This section may depend on packages your system does NOT have pre-installed. Ensure you do not skip commands for installation if any exist.

<div align="center">
<a href=""><img src="../../../../assets/.png" alt="[Missing Content] Screenshot of a Terminal window completing this section."></a>
</div>

<p align="center">Once you're ready to continue, head to the next page.</p>

<h2 align="center">
  <br>
  <div>
    <a class="top-button" href="#">&uarr; Go to Top &uarr;</a>
  </div>
  <br>
</h2>
