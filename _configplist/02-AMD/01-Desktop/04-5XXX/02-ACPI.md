---
layout: default
title: ACPI
parent: Ryzen 5000 Series
grand_parent: Desktop CPUs
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

<a align="center" href=""><img src="../../../../assets/" alt="Screenshot of ACPI Section in ProperTree"></a>

<h1 class="section-title">ACPI</h1>

<h2 class="key-title">Add</h2>

This section of the config is meant to expose the various ACPI in your OC folder. This along with many of the other sections will be auto-filled by simply going to ``File -> OC (Clean) Snapshot`` and selecting the root OC folder in your USB. This step may have already been done, no need to redo. If everything shows up, we won't have to make any changes.

<h2 class="key-title">Delete</h2>

Here you can define tables that are to be removed from the ACPI stack. However, it is not relevant for us, so we can keep scrolling.

<h2 class="key-title">Patch</h2>

Makes individual patches to the ACPI tables. This shouldn't be relevant for us as Ryzen 5000 usually doesn't require IRQ patches.

<h2 class="key-title">Quirks</h2>

This section has settings related to compatibility and workarounds for issues in firmware or OS handling of ACPI.
The settings can be left as listed below for almost all systems.

| Key              | Value | Description                                                                                                                                                                                                                                               |
| ---------------- | ----- | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| FadtEnableReset  | False | Only relevant on legacy hardware (pre 2009) when shutting down results in a reboot. The FADT table (Fixed ACPI Description Table) is in some cases too small to contain the required reset code - OpenCore tries to add the code with this quirk enabled. |
| NormalizeHeaders | False | Used for cleaning up ACPI headers in [High Sierra](https://alextjam.es/debugging-appleacpiplatform/) - If you don't plan to install High Sierra, you won't need this quirk.                                                                               |
| RebaseRegions    | False |                                                                                                                                                                                                                                                      |
| ResetHwSig       | False |                                                                                                                                                                                                                                                   |
| ResetLogoStatus  | False | Needed on systems where the BIOS splash screen gets stuck and won't clear - recent AMD systems shouldn't need it.                                                                                                                                         |
| SyncTableIds     | False |                                                                                                                                                                                                                                                 |

<h2 align="center">
  <br>
  <div class="navigation-container">
    <a class="nav-button" href="../01-Introduction/">&larr; Back Page</a>
    <a class="nav-button" href="../03-Booter/">Next Page &rarr;</a>
  </div>
  <br>
</h2>
