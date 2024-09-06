---
layout: default
title: Kexts
nav_order: 4
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
  <img width="650" height="200" src="../../../assets/Header-OpenCore-Kexts.png">
</p>

<h2 align="center">Placeholder Information</h2>

<h4 align="center">This page is a stub, but this page should:</h4>
<br>

1. List known Kexts and chart them, as well as advising which are required, and which can be added later.

2. Note what, hopefully, all kexts do, even if they're not needed or are about initially booting recoveryOS; Having the information in a central page will be useful for those who want to think for themselves in post-install, and add additional kexts.

## What are "kexts" and why do we care about them?

A kext (short for kernel extension) is an extension of the kernel in macOS. These extensions make it possible to extend the functionality of the operating system without having to recompile the kernel itself. Kexts are similar to drivers in Windows because they allow the kernel to communicate with the computer's hardware and are often used to add support for new hardware or improve existing hardware features. Kext files are actually bundles that contain multiple files, similar to ZIP archives, but are not compressed - that's why they appear as folders in Windows or Linux. In macOS, you can view the contents of a kext file by right-clicking it and selecting “Show Package Contents”, in other OS, you can simply treat them like folders.

However, Apple has started to <a href="https://support.apple.com/guide/deployment/system-and-kernel-extensions-in-macos-depa5fb8376f/web">reduce the use of kexts</a> , especially since macOS Big Sur, as they can cause security issues. For us, they are essential to get macOS running.

What follows is a list of all kexts that exist (or are at least publicly available). However, this does not mean that you need them - follow the corresponding table,

### Generic kexts


#### <a href="https://github.com/acidanthera/Lilu">Lilu</a>
Lilu serves as the fundamental kext for the majority of other kexts. It functions as a patching engine, enabling other kexts to perform non-destructive modifications to the system. Additionally, it functions as a library patcher.

Lilu supports all macOS versions (OSX 10.4 Tiger to macOS 14 Sonoma).

### CPU and SMC kexts
You may have noticed that Macs have always come with a very limited variety of hardware. This is because the operating system is not designed for broad compatibility, but rather for maximum customization. After all, why support more hardware if you are the sole manufacturer? We don't have the exact hardware that was built into Macs. Therefore we need to patch the kernel according to our hardware and have to deal with Apple's System Management Controller (SMC).

#### <a href="https://github.com/acidanthera/VirtualSMC">VirtualSMC</a>
Acidanthera's VirtualSMC emulates Apple's SMC inside the kernel. It is essential for running macOS on non-native hardware. Virtual SMC comes with several plugins listed below.

VirtualSMC supports all macOS versions (10.4 Tiger to macOS 14 Sonoma).

<h2 align="center">
  <br>
  <div class="next-button-container">
  <a class="next-button" href="../05-Resources/index/">Next Page &rarr;</a>
  </div>
  <br>
</h2>
