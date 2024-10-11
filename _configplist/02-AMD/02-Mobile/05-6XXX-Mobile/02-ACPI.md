---
layout: default
title: ACPI
parent: Ryzen 6000 Mobile Series
grand_parent: Mobile CPUs
nav_order: 2
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

  .section-title{
    text-align: center
  }

  .key-title{
    text-align: left
  }
</style>

<a align="center" href=""><img src="../../../../../assets/" alt="Screenshot of ACPI Section in ProperTree"></a>

<h1 class="section-title">ACPI</h1>

<h2 class="key-title">Add</h2>

This section of the config is meant to expose the various ACPI in your OC folder. This along with many of the other sections will be auto-filled by simply going to ``File -> OC Clean Snapshot`` and selecting the root OC folder in your USB. This step may have already been done, no need to redo.

<h2 class="key-title">Delete</h2>

This blocks certain ACPI tables from loading, for us, we can ignore this.

<h2 class="key-title">Patch</h2>

This section allows us to dynamically modify parts of the ACPI (DSDT, SSDT, etc.) via OpenCore. For us, our patches are handled by our SSDTs. This is a much cleaner solution as this will allow us to boot Windows and other OSes with OpenCore for dual or multi-boot configurations.

<h2 class="key-title">Quirks</h2>

Placeholder text for this section

| Key | Type | Value |
| --- | --- | --- |
| FadtEnableReset | Boolean | False |
| NormalizeHeaders | Boolean | False |
| RebaseRegions | Boolean | False |
| ResetHwSig | Boolean | False |
| ResetLogoStatus | Boolean | True |
| SyncTableIds | Boolean | False |

<h2 align="center">
  <br>
  <div class="navigation-container">
    <a class="nav-button" href="../01-Introduction/">&larr; Back Page</a>
    <a class="nav-button" href="../03-Booter/">Next Page &rarr;</a>
  </div>
  <br>
</h2>
