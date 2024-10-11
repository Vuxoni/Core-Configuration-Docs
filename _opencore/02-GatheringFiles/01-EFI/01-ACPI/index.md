---
layout: default
title: ACPI
parent: EFI Setup
grand_parent: Gathering Files
description: 
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

  .manual-next-button-container {
    text-align: right;
  }

  .manual-next-button {
    margin: 10px;
    top: 0px;
    bottom: 0px;
    left: 0px;
    right: 0px;
  }
</style>

<p align="center">
  <img width="650" height="200" src="../../../../../assets/Headers/Header-OpenCore-ACPI.png">
</p>

<h2 align="center">How to provide OpenCore the proper SSDTs for your system</h2>
<br>

{: .internalnote }
This is to go over what ACPI is, what it does, why we need to sometimes patch ACPI, and any other relevent information, We end up by leading the user to using SSDTTime, but also provide a Manual section for future reference when we write information about specific SSDTs and how they work/are made, can be made by hand.

<h2 align="center">
  <br>
  <div class="manual-next-button-container">
  <a class="manual-next-button" href="../02-Manual/index/">Manual SSDT Creation &rarr;</a>
  </div>
  <div class="navigation-container">
    <a class="nav-button" href="../../index/">&larr; Back Page</a>
    <a class="nav-button" href="../01-SSDTTime/index">SSDTTime Usage &rarr;</a>
  </div>
  <br>
</h2>

