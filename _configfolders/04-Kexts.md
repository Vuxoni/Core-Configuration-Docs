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

## Generic kexts

### <a href="https://github.com/acidanthera/Lilu">Lilu</a>
Lilu functions as a patching engine, enabling other kexts to perform non-destructive modifications to the system. Additionally, it functions as a “patch engine” that a lot of kexts depend on it for patching frameworks at kernel runtime. Without Lilu, they will fail to inject. In other words: Without Lilu, almost everything comes to a standstill.
Lilu supports all macOS versions (OS X 10.4 Tiger to macOS 14 Sonoma).

## CPU and SMC kexts
You may have noticed that Macs have always come with a very limited variety of hardware. This is because the operating system is not designed for broad compatibility, but rather for maximum customization. After all, why support more hardware if you are the sole manufacturer? We don't have the exact hardware that was built into Macs. Therefore we need to patch the kernel according to our hardware and have to deal with Apple's System Management Controller (SMC).

### <a href="https://github.com/acidanthera/VirtualSMC">VirtualSMC</a>
Acidanthera's VirtualSMC emulates Apple's SMC found on real Macs inside the kernel. It is essential for running macOS on non-native hardware. Virtual SMC is also the base kext for several plugins listed below that add support for sensors.
VirtualSMC supports all macOS versions (OS X 10.4 Tiger to macOS 14 Sonoma).

Add later, probably in troubleshooting/panic section: Why does VirtualSMC show in every page fault kernel panic?
In most cases VirtualSMC is unrelated to any kernel panic you experience. The reason it is present in stacktrace is becauase VirtualSMC wraps kernel_trap to emulate SMC device.

### SMCBatteryManager
SMCBatteryManager is a VirtualSMC that provides detailed battery information, including the current percentage. As the name suggests, it requires you to have a battery, therefore you shouldn't use it on Desktops.
SMCBatteryManager supports all macOS versions (OS X 10.4 Tiger to macOS 14 Sonoma).

### SMCDellSensors
SMCDellSensors is a plugin for VirtualSMC. This plugin is specifically designed to support Dell laptops and desktops by providing sensor data to macOS. As the name suggests, it requires you to have a system manufactured by Dell. Don't use it if you don't have a Dell machine.
SMCDellSensors supports OS X 10.7 Lion to macOS 14 Sonoma.

### SMCLightSensor
SMCLighSensor is a plugin for VirtualSMC. This plugin is specifically designed to provide ambient light sensor data to macOS, allowing the system to adjust screen brightness and other settings based on the surrounding light conditions. This kext requires a light sensor, which is typically found only in higher-end laptops. If your laptop doesn’t support automatic brightness adjustment in Windows, this kext won’t function. When in doubt, it’s best to skip it.
SMCLightSensor supports OS X 10.6 Snow Leopard to macOS 14 Sonoma.

### SMCProcessor
SMCProcessor is a VirtualSMC plugin used to read CPU temperature on Intel based systems (Penryn and newer).
SMCProcessor supports OS X 10.7 Lion to macOS 14 Sonoma.

### <a href="https://github.com/trulyspinach/SMCAMDProcessor">SMCAMDProcessor & AMDRyzenCPUPowerManagement</a>
SMCAMDProcessor is the counterpart to SMCProcessor that comes bundled with AMDRyzenCPUPowerManagement. 
AMDRyzenCPUPowerManagement (that is actually not a VirtualSMC plugin) provides power management features for AMD Processors. SMCAMDProcessor is a VirtualSMC plugin that collects sensor data - however, you can't use it without AMDRyzenCPUPowerManagement.
In addition, these kexts allow PState editing and manual switching of clock speeds inside the bundled AMD Power Gadget tool.
Note that SMCAMDProcessor & AMDRyzenCPUPowermanagement don't work as intended on AMD based laptops. Using these kexts may result in increased temperatures and reduced battery life.

In theory, SMCAMDProcessor and AMDRyzenCPUPowerManagement support OS X 10.8 Mountain Lion up to macOS 14 Sonoma. However, AMD support (without a lot of patching) is only available in macOS 10.13 High Sierra to macOS 14 Sonoma.

### <a href="https://github.com/macos86/SMCProcessorAMD">SMCProcessorAMD</a>
SMCProcessorAMD is very similar to SMCAMDProcessor. The key difference is that SMCAMDProcessor is dependent on AMDRyzenCPUPowerManagement - if you don't want to use AMDRyzenCPUPowerManagement for some reason (e.g. you own a laptop), you can use SMCProcessorAMD.
SMCDellSensors supports OS X 10.7 Mountain Lion High Sierra to macOS 14 Sonoma.

### <a href="https://github.com/hieplpvip/AsusSMC">AsusSMC</a>
AsusSMC is a VirtualSMC plugin that provides support for built-in Ambient Light Sensors (ALS), keyboard backlight controll, battery sensors and Fn key support on Asus laptops. As the name suggests, this only applies to Asus laptops.
In theory, AsusSMC supports OS X 10.8 Mountain Lion up to macOS 14 Sonoma.

### <a href="https://github.com/zhen-zen/YogaSMC">YogaSMC</a> 
Just as AsusSMC, YogaSMC is a VirtualSMC plugin that provides sensor readings to the SMC. As the name suggests, this only applies to Lenovo laptops. Make sure to read the readMe if you have such a Lenovo laptop.
It is not known to us which versions YogaSMC supports. Please let us know which ones are possible.

### <a href="https://github.com/Xiashangning/BigSurface">BigSurface</a> 
BigSurface is, among other things, a VirtualSMC plugin that provides sensor data to the SMC on certain Surface devices. Read the ReadMe if you have a Microsoft device.
In theory, BigSurface supports macOS 10.12 Sierra up to macOS 14 Sonoma.

### SMCSuperIO
SMCSuperIO is a VirtualSMC plugin that can read and edit fan speeds. It may require additional patching. 
SMCLightSensor supports OS X 10.6 Snow Leopard to macOS 14 Sonoma.

### <a href="https://github.com/ChefKissInc/SMCRadeonSensors">SMCRadeonSensors</a> 
SMCRadeonSensors is a VirtualSMC plugin that provides temperature readings on AMD GPUs.
SMCRadeonSensors supports macOS 10.14 Mojave up to macOS 14 Sonoma.

<h2 align="center">
  <br>
  <div class="next-button-container">
  <a class="next-button" href="../05-Resources/index/">Next Page &rarr;</a>
  </div>
  <br>
</h2>
