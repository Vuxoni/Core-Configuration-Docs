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
</style>

<p align="center">
  <img width="650" height="200" src="../../../../assets/Headers/Header-UsingWindows.png">
</p>

<h2 align="center">Get ready to keep track of your info!</h2>
<br>

## What are we looking for?

Start by verifying that your CPU, motherboard, and GPU are supported by macOS. It’s essential to check that your storage devices, such as NVMe drives, are recognized and perform well with macOS.
Ensuring compatibility with network and audio components is also important for a smooth experience.
In many cases it still makes sense to check how old your firmware is.

## Gathering HWInfo64

In order to get the most information from our system, we want to use [HWiNFO64](https://www.hwinfo.com/download/). It's up to you if you want to get the installer or the portable version.
Once we downloaded HWiNFO64, we can open the program. 

<div style="text-align: center;" markdown="1">
  [![HWiNFO64 Summary](/assets/HWiNFO64/Summary.png)](/assets/HWiNFO64/Summary.png)
</div>

Now that we see the summary, we can check whether our hardware is supported. Please write down:
- The CPU model and codename
- The GPU model and codename
- Your chipset and BIOS date
- The models of your drives at the bottom right

After that we want to find out the Ethernet controller and, if you have one, the WiFi controller.
To do this, we look at the extended information from HWiNFO. Here we see the Audio and Network tabs.

<div style="text-align: center;" markdown="1">
[![HWiNFO64 Extended](/assets/HWiNFO64/Extended.png)](/assets/HWiNFO64/Extended.png) 
</div>

<!---
To be swapped out with a real screenshot
--->

As we can see, this Ethernet controller is called Realtek RTL8125. The WLAN chip, on the other hand, is a Broadcom BRCM4360CD.

Now that we've written that down, we can now go ahead and see if the hardware is supported.

<h2 align="center">
  <br>
  <div class="navigation-container">
    <a class="nav-button" href="../../../03-KnowYourHardware/index">&larr; Back Page</a>
    <a class="nav-button" href="../../../04-CompatibilityCharts/index">Next Page &rarr;</a>
  </div>
  <br>
</h2>
