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
</style>

<p align="center">
  <img width="650" height="200" src="../../../assets/Headers/Header-Introduction.png">
</p>

<h2 align="center">What is OpenCore? How can we use it?</h2>
<br>

OpenCore is known as a custom bootloader that has the unique ability to see, and boot HFS+ and APFS disks and disk images. In the world of UEFI firmware, you can run what are essentially binaries such as bootloaders you're familiar with, like GRUB or the Windows Boot Manager.

OpenCore unlike other bootloaders, has to be manually configured to properly boot the Mac operating system. This is where you are able to use OpenCore to your advantage. Issues you are aware of, can be fixed with enough persistence and proper configuration. 

As .efi files are simply bootable by most UEFI firmwares via a USB, we can use a flash drive to configure OpenCore until we are satisfied it is as complete as it can be. This allows us to quickly modify ``config.plist`` and reboot to quickly prototype these changes. Later, during Post Installation, when we are satisfied with our results of our EFI you can install it to the usual EFI partition that exists on your disk. This removes the necessity to use a USB to boot OS X / macOS.

<br>
To continue in this guide you will require:

- USB Flash Drive (4GB+)
- 10GB Free Space on Disk

<br>
Begin by formatting your USB to FAT32, when you are ready please continue.

<h2 align="center">
  <br>
  <div class="navigation-container">
    <a class="nav-button" href="../../hardware/04-CompatibilityCharts/05-Misc/index">&larr; Back Page</a>
    <a class="nav-button" href="../02-GatheringFiles/index">Next Page &rarr;</a>
  </div>
  <br>
</h2>
