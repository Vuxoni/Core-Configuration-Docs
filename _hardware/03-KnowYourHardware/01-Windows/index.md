---
layout: default
title: Windows
parent: Know Your hardware
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

  .image-container {
    display: flex;
    justify-content: space-around;
    align-items: center;
    margin: 20px 0;
  }

  .image-item {
    text-align: center;
    max-width: 300px;
    margin: 0 10px;
  }

  .image-item img {
    max-width: 100%;
    height: auto;
  }
</style>

<p align="center">
  <img width="650" height="200" src="../../../../assets/Headers/Header-UsingWindows.png">
</p>

<h2 align="center">Get ready to keep track of your info!</h2>
<br>

<h2 align="center">What are we looking for?</h2>
<br>

<p align="center">We'll start by writing down the CPU, Motherboard, and GPU information. It’s essential to check that your storage devices, such as NVMe drives, are recognized and perform well with macOS as well.</p>

<p align="center">Ensuring compatibility with Network and Audio devices is also important for a smooth experience. In many cases it still makes sense to check how old your motherboard firmware (BIOS) is, and update it if necessary. This reduces the chances of future updates breaking your ACPI.</p>

<h2 align="center">Using HWiNFO</h2>
<br>

{: .note }
In order to easily get the most information from our system, we'll want to use <a href="https://www.hwinfo.com/download/">HWiNFO</a>. It's free and lightweight. Once we have HWiNFO, we can open the program and begin searching for information. You will get an initial popup you can continue on for a Summary page to open.

<br>
<p align="center">Below is the Summary window that will appear on initial launch.</p>

<div align="center">
<a href=""><img src="../../../../assets/HWiNFO64/SystemSummary.png" alt=""></a>
</div>

<p align="center">While further information can be found in the Full Summary window.</p>

<div align="center">
<a href=""><img src="../../../../assets/HWiNFO64/FullSummaryWindow.png" alt=""></a>
</div>

<p align="center">Now that you're familiar with the program, let's move on.</p>
<br>

<hr>
<h3 align="center">Finding CPU Name</h3>

<p align="center">To begin, you can quickly find out your CPU Name and Codename with the System Summary that appeared. The upper left corner displays the following useful information:</p>

<div align="center">
<a href=""><img src="../../../../assets/HWiNFO64/SystemSummaryCPUName.png" alt=""></a>
</div>

<p align="center">If you want to use the full summary, you can navigate the left-hand bar to find the following entry:</p>

```bash
YourMachineName -> Motherboard -> SMBIOS DMI -> Processor
```

<div align="center">
<a href=""><img src="../../../../assets/HWiNFO64/CPUNameGeneration.png" alt=""></a>
</div>

<hr>
<h3 align="center">Finding GPU Information</h3>

<p align="center">Using the System Summary we can see on the top right, is the GPU information we can note down.</p>

<div align="center">
<a href=""><img src="../../../../assets/HWiNFO64/SystemSummaryGPUName.png" alt=""></a>
</div>

<p align="center">If you'd like to use the full system summary, you can go to the following path:</p>

```bash
YourMachineName -> Video Adapter -> GPU Name
```

<div align="center">
<a href=""><img src="../../../../assets/HWiNFO64/GPUNameInfo.png" alt=""></a>
</div>

<p align="center">This would be required for those who need to know the PciRoot path of their devices. Used for OpenCore's DeviceProperties section, when injecting or removing certain data.</p>

<p align="center">This section also gives you the Vendor and Device ID if a Helper asks for that information, when verifying a specific non-specifically named GPU device like Radeon Graphics.</p>

<hr>
<h3 align="center">Finding Motherboard Name/Chipset</h3>

<p align="center">Using the System Summary, in the middle top area you will get basic information on the motherboard.</p>

<div align="center">
<a href=""><img src="../../../../assets/HWiNFO64/SystemSummaryMotherboard.png" alt=""></a>
</div>

<p align="center">If you require more information, you can go to the following paths:</p>

```bash
YourMachineName -> Motherboard -> SMBIOS DMI -> Mainboard
```

<div align="center">
<a href=""><img src="../../../../assets/HWiNFO64/MotherboardChipsetName.png" alt=""></a>
</div>

```bash
YourMachineName -> Motherboard -> SMBIOS DMI -> BIOS 
```

<div align="center">
<a href=""><img src="../../../../assets/HWiNFO64/MotherboardBIOSInfo.png" alt=""></a>
</div>

<hr>
<h3 align="center">Finding Storage Name/Model/Type</h3>

<p align="center">You can quickly find basic information such as the Interface Type and Name of your storage in the bottom right corner of the System Summary.</p>

<div align="center">
<a href=""><img src="../../../../assets/HWiNFO64/SystemSummaryStorage.png" alt=""></a>
</div>

<p align="center">If you require deeper information, you can go to the following path:</p>

```bash
YourMachineName -> Drives -> Type -> Name
```

<div align="center">
<a href=""><img src="../../../../assets/HWiNFO64/StorageTypeBrandName.png" alt=""></a>
</div>

<p align="center">If you need to get the specific PciRoot that the specific Drive you're looking at is, you can click the <code>Host Controller</code> value to be redirected to it.</p>

<div align="center">
<a href=""><img src="../../../../assets/HWiNFO64/NVMeControllerPciRoot.png" alt=""></a>
</div>

<p align="center">As you can see above, you can now write or copy/paste the PciRoot data.</p>

<hr>
<h3 align="center">Finding Networking Controllers</h3>

<p align="center">You'll need to use the Full System Summary window to view this data.</p>

```bash
YourMachineName -> Network -> Device Name
```

<div align="center">
<a href=""><img src="../../../../assets/HWiNFO64/NetworkingSidebar.png" alt=""></a>
</div>

<p align="center">Depending on what you have, you may only see Ethernet or Wi-Fi, maybe both!</p>

<div align="center">
<a href=""><img src="../../../../assets/HWiNFO64/NetworkingEthernet.png" alt=""></a>
</div>

<p align="center">This is an example of a laptop wireless networking card below.</p>

<div align="center">
<a href=""><img src="../../../../assets/HWiNFO64/NetworkingWireless.png" alt=""></a>
</div>

<p align="center">This is a great way to find out the Name, Chipset, and the PciRoot of your networking interface of choice.</p>

<hr>
<h3 align="center">Finding Sound Controller and Codecs</h3>

<p align="center">You'll need to use the Full System Summary window to view this data.</p>

```bash
YourMachineName -> Audio -> Audio Controller Name
```

<div align="center">
<a href=""><img src="../../../../assets/HWiNFO64/AudioChipsetCodec.png" alt=""></a>
</div>

<p align="center">In the above screenshot, we can see that this specific Audio Controller on the example motherboard, has an <code>ALC1220</code> Codec, and the Vendor/Device ID are visible to note down as well.</p>

<div align="center">
<a href=""><img src="../../../../assets/HWiNFO64/AudioChipsetCodecMobile.png" alt=""></a>
</div>

<p align="center">Here's a laptop in HWiNFO64, displaying the codec for the sound controller as <code>ALC285</code> for the motherboard and the Vendor/Device ID are visible to note down as well.</p>

<hr>
<h3 align="center">Finding Input Devices and Type</h3>

{: .internalnote }
This section is a placeholder outline for Contributors to fill in! Thank you for this, I have 0 laptop experience :P The plan here is to first find the Trackpad/Touchpad, and determine its type, then we move on and figure out Keyboard.

{: .note }
This section is specific to Mobile platforms, such as Laptops and Handhelds. If you are on a Desktop, you can safely skip this section of the instructions.

<p align="center">When it comes to mobile devices such as Laptops and handheld devices, <b>you'll need to use Device Manager, not HWiNFO64</b> to determine the way that your input devices are wired to the machine.</p>

<p align="center">This means that, while on a Desktop you typically always see USB based Keyboard and Mice, Mobile devices tend to use one of the following 4 types of Input devices, in a mixed/matched way for either the trackpad or keyboard:</p>
<br>

- I2C

- SMBus

- PS/2

- USB

<br>
<p align="center">This is important because you'll actually have to use specific UEFI Drivers or Kernel Extensions to make use of these devices under OpenCore and OS X / macOS respectively. It'll be more than important to know this information now for later when deciding what files you'll be gathering.</p>

<p align="center">To get started, begin by opening a new Device Manager window by right clicking your Start Menu and selecting <code>Device Manager</code> to get a new fresh window like so:</p>

<div align="center">
<a href=""><img src="../../../../assets/DeviceManager/FreshWindow.png" alt="Fresh Device Manager Window" style="width:60%;"></a>
</div>

<p align="center">We're going to want to click on <code>View -> Device by Connection</code>

<div class="image-container">
  <div class="image-item">
    <h3>Dropdown Menu</h3>
    <a href="../../../../assets/DeviceManager/ByConnectionDropDown.png" target="_blank">
      <img src="../../../../assets/DeviceManager/ByConnectionDropDown.png" alt="Dropdown Menu">
    </a>
  </div>
  <div class="image-item">
    <h3>New Window Appearance</h3>
    <a href="../../../../assets/DeviceManager/ByConnectionWindow.png" target="_blank">
      <img src="../../../../assets/DeviceManager/ByConnectionWindow.png" alt="New Window Appearance">
    </a>
  </div>
</div>

<p align="center">Placeholder Step.</p>

<div align="center">
<a href=""><img src="../../../../assets/DeviceManager/Placeholder.png" alt="[Missing Content] Placeholder"></a>
</div>

<p align="center">Placeholder Step.</p>

<div align="center">
<a href=""><img src="../../../../assets/DeviceManager/Placeholder.png" alt="[Missing Content] Placeholder"></a>
</div>

<p align="center">Placeholder Step.</p>

<div align="center">
<a href=""><img src="../../../../assets/DeviceManager/Placeholder.png" alt="[Missing Content] Placeholder"></a>
</div>

<hr>

<h2 align="center">Congratulations!</h2>

<br>
<p align="center">Now that we've written all of that down, we can now go ahead and see if the hardware is supported.</p>

<h2 align="center">
  <br>
  <div class="navigation-container">
    <a class="nav-button" href="../../../03-KnowYourHardware/index">&larr; Back Page</a>
    <a class="nav-button" href="../../../04-CompatibilityCharts/index">Next Page &rarr;</a>
  </div>
  <br>
</h2>
