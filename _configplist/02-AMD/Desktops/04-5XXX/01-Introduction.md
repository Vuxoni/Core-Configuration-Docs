---
layout: default
title: Introduction
parent: Ryzen 5000 series
grand_parent: AMD Desktop CPUs
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
  <img width="650" height="200" src="../../../../../assets/Header-Placeholder.png">
</p>

<h4 align="center">This page is a stub, we have enabled the ToC for the moment, but this page should:</h4>
<br>

1. Explain issues or known prerequisites for this CPU
2. Allows any other information to be mentioned here, prior to configuring OpenCore

Like earlier Ryzen CPUs, the Ryzen 5000 series has only a few concerns for getting them working.

- Supported by several generations of Socket AM4 chipsets, specific configuration depends on the motherboard and firmware.
- Requires the use of AMD vanilla kernel patches.
- No 32-bit OS or software support like with all AMD CPUs.
- Recommended OSs are macOS 10.15 Catalina through macOS 14 Sonoma due to the above.
- "G" models with integrated graphics are supported by the NootedRed project for accelerated graphics.

<h2 align="center">
  <br>
  <div class="navigation-container">
    <a class="nav-button" href="../index/">&larr; Back Page</a>
    <a class="nav-button" href="../02-ACPI/">Next Page &rarr;</a>
  </div>
  <br>
</h2>
