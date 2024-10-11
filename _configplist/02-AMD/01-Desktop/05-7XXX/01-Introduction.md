---
layout: default
title: Introduction
parent: Ryzen 7000 Series
grand_parent: Desktop CPUs
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
  <img width="650" height="200" src="../../../../assets/Header-Placeholder.png">
</p>

<h4 align="center">This page is a stub, we have enabled the ToC for the moment, but this page should:</h4>
<br>

1. Explain issues or known prerequisites for this CPU
2. Allows any other information to be mentioned here, prior to configuring OpenCore

Configuration remains similar to previous Ryzen, except for needing to set up a correct MMIO whitelist. This will be covered in the Booter section.
Nearly all Ryzen 7000 series desktop CPUs have integrated graphics, but there is currently no way to enable this for macOS.

- Certain motherboards are difficult and recent firmwares with Ryzen 8000 series CPU support can have ACPI errors.
- Requires the use of AMD vanilla kernel patches.
- No 32-bit OS or software support like with all AMD CPUs.
- Recommended OSs are macOS 10.15 Catalina through macOS 14 Sonoma due to the above.
- Despite the presence of integrated graphics, accelerated graphics cannot be enabled with current community projects.



<h2 align="center">
  <br>
  <div class="navigation-container">
    <a class="nav-button" href="../index/">&larr; Back Page</a>
    <a class="nav-button" href="../02-ACPI/">Next Page &rarr;</a>
  </div>
  <br>
</h2>
