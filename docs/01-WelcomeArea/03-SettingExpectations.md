---
layout: default
title: Setting Expectations
description: Focused on explaining the kind of experience you can expect depending on your hardware.
parent: Welcome to the Botánica
nav_order: 3
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
  <img width="650" height="200" src="../../assets/Headers/Header-SettingExpectations.png">
</p>

<h2 align="center">What makes a Mac special?</h2>
<br>
<p align="center">It's important to understand that the Mac operating system is not inherently special in any way that actively prevents usage (Besides a few examples) on Non-Apple hardware. Real Mac machines have a different kind of UEFI/EFI/BIOS firmware (Whatever you feel is most accurate) that has native support for finding, and more importantly, booting HFS(+) and APFS volumes/disks/drives. The first roadblock for PC's is the inability to locate OS X / macOS formatted disks. The second roadblock, is no boot code to actively load the kernel into memory and proceed with boot, as a Mac would know to do.</p>

<h2 align="center">How does OpenCore solve these issue?</h2>
<br>
<p align="center"><a href="https://github.com/acidanthera/OpenCorePkg">OpenCorePkg</a> more specifically, is an <a href="https://github.com/tianocore/edk2">EDKII</a> package that extends the UEFI reference firmware (What OEMs and other UEFI firmware developers use as the reference for UEFI) with the ability to locate, read, and boot HFS(+) and APFS volumes/disks/drives. Talented developers like <a href="https://github.com/vit9696">vit9696</a> and <a href="https://github.com/mhaeuser">mhaeuser</a>, along with the core Acidanthera team/contributors have taken the time to create a <code>Library Set</code> that provides supplemental functionality for Apple-specific UEFI drivers.</p>

<p align="center">What does this mean for you? <b>It means that you have the chance to download the OpenCore bootloader, configure it to describe and patch your machine to/for OS X / macOS, and achieve a fully bootable, non-invasive, vanilla form of the Mac operating system, with Security and Integrity in mind.</b></p>

<p align="center">The purpose of these Docs is to ensure a User has the ability to understand how to use the OpenCore bootloader to accomplish various tasks, helping achieve a bootable and working system, with additional Docs for perfecting and refining the system. There's loads of settings and knobs available, but how do you know what's what? We're here to explain and help!</p>

<h2 align="center">So, where do the issues happen?</h2>
<br>
<p align="center"><b>Hardware!</b> Unfortunately for us, while the operating system itself is not special, it does not mean we don't deal with basic issues. Windows is an incredibly old operating system in terms of what hardware it can support OOB (Out-of-Box) such as incredibly old NVIDIA Graphics Processing Units even on Windows 10 and 11. If you've ever built your own computer and had to install Windows from a USB stick, you know that the initial installation lacks a lot of drivers. One such visible example is, your new RTX 4090 Ti does not have drivers pre-installed on Windows 10, so you go ahead and download the installer executable from NVIDIA's website, and after a reboot you now have graphics acceleration!</p>

<p align="center">OS X / macOS doesn't work that way. One does not simply download "drivers" for their hardware on a Mac, unless it is third party external hardware like physical mixers for audio production and the likes. The Mac operating system uses a file format known as "Kext" which is shorthand for Kernel Extension. The Mac operating system bundles kexts for the hardware you find on a Mac. For this reason, your shiny RTX cannot be used on OS X / macOS, because there has never been a Mac that released, and utilized an RTX card for Graphics. This is very important to understand, hardware support comes from the OS itself, and any third party drivers you find that are developed by the community, are just that: third-party and not native support.</p>

<p align="center">Unfortunately, this is true for a lot of hardware, not just GPUs. You can only ever expect full hardware support by purchasing a real Mac computer. Our goal is to ensure our off-the-shelf hardware, can be used by these bundled kernel extensions, or atleast in some capacity have had third party developers introduce support for said hardware. You now understand the basic issue when it comes to wanting to run OS X / macOS on your hardware, <b>it simply may not be supported.</b></p>

<h2 align="center">But, Apple doesn't make Intel Macs anymore... right?</h2>
<br>
<p align="center">Correct. As far as we can tell, the hardware support charts can be completed and fleshed out, while also being the most up-to-date information, due to no new hardware being used and added for support. Because of this, we'll need to talk about the future of macOS on x86_64 CPUs.</p>

<h2 align="center">
  <br>
  <div class="navigation-container">
    <a class="nav-button" href="02-WhatFollowsNext.html">&larr; Back Page</a>
    <a class="nav-button" href="04-FutureOfx86.html">Next Page &rarr;</a>
  </div>
  <br>
</h2>
