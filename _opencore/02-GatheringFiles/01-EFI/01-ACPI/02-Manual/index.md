---
layout: default
title: Manually
parent: ACPI
grand_parent: EFI Setup
nav_order: 2
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

  .SSDT-button-container {
    text-align: right;
  }

  .SSDT-next-button {
    margin: 10px;
    top: 0px;
    bottom: 0px;
    left: 0px;
    right: 0px;
  }
</style>

<p align="center">
  <img width="650" height="200" src="../../../../../../assets/Headers/Header-Method-Manual.png">
</p>

When it comes to using Prebuilt SSDTs they tend to work for the majority of users, but clearly do not teach anything to the end-user. For nearly all users though, **we still recommend going back to the previous page and using CorpNewt's SSDTTime to quicky generate SSDTs from the target machine** as this tends to be a bit better than simply downloading precompiled SSDTs that attempt to generically support many devices by first dumping your DSDT and using that, for automated creation. 

For the die-hard users who are interested in not only learning how to create specific SSDTs but want to jump deeper in to what each SSDT is actually doing and why, feel free to choose below to begin.

In the previous page, you went over what SSDTs may be required for your system, but we understand that in some scenarios, you'll want to actually create entirely new SSDTs that are not present in SSDTTime, or were not previously mentioned to exist.

<h2 align="center">
  <br>
  <div class="SSDT-button-container">
  <a class="SSDT-next-button" href="../01-SSDT-AWAC">SSDT-AWAC &rarr;</a>
  </div>
  <div class="SSDT-button-container">
  <a class="SSDT-next-button" href="../02-SSDT-CPUR">SSDT-CPUR &rarr;</a>
  </div>
  <div class="SSDT-button-container">
  <a class="SSDT-next-button" href="../03-SSDT-BRIDGE">SSDT-BRIDGE &rarr;</a>
  </div>
  <div class="SSDT-button-container">
  <a class="SSDT-next-button" href="../04-SSDT-EC">SSDT-EC &rarr;</a>
  </div>
  <div class="SSDT-button-container">
  <a class="SSDT-next-button" href="../05-SSDT-USBX">SSDT-USBX &rarr;</a>
  </div>
  <div class="SSDT-button-container">
  <a class="SSDT-next-button" href="../06-SSDT-GPI0">SSDT-GPI0 &rarr;</a>
  </div>
  <div class="SSDT-button-container">
  <a class="SSDT-next-button" href="../07-SSDT-DEVICE-DISABLE">SSDT-DEVICE-DISABLE &rarr;</a>
  </div>
  <div class="SSDT-button-container">
  <a class="SSDT-next-button" href="../08-SSDT-DEVICE-SPOOF">SSDT-DEVICE-SPOOF &rarr;</a>
  </div>
  <div class="SSDT-button-container">
  <a class="SSDT-next-button" href="../09-SSDT-IMEI">SSDT-IMEI &rarr;</a>
  </div>
  <div class="SSDT-button-container">
  <a class="SSDT-next-button" href="../10-SSDT-PLUG">SSDT-PLUG &rarr;</a>
  </div>
  <div class="SSDT-button-container">
  <a class="SSDT-next-button" href="../11-SSDT-PMC">SSDT-PMC &rarr;</a>
  </div>
  <div class="SSDT-button-container">
  <a class="SSDT-next-button" href="../12-SSDT-PNLF">SSDT-PNLF &rarr;</a>
  </div>
  <div class="SSDT-button-container">
  <a class="SSDT-next-button" href="../13-SSDT-RHUB">SSDT-RHUB &rarr;</a>
  </div>
  <div class="SSDT-button-container">
  <a class="SSDT-next-button" href="../14-SSDT-RTC">SSDT-RTC &rarr;</a>
  </div>
  <div class="SSDT-button-container">
  <a class="SSDT-next-button" href="../15-SSDT-UNC">SSDT-UNC &rarr;</a>
  </div>
  <div class="navigation-container">
    <a class="nav-button" href="../../index/">&larr; Back Page</a>
    <a class="nav-button" href="../16-SSDT-XOSI">SSDT-XOSI &rarr;</a>
  </div>
  <br>
</h2>
