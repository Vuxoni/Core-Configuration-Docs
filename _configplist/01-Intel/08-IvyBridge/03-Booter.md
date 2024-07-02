---
layout: default
title: Booter
parent: Ivybridge
grand_parent: Intel CPUs
nav_order: 3
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

<a align="center" href=""><img src="../../../../assets/" alt="Screenshot of Booter Section in ProperTree"></a>

<h1 class="section-title">Booter</h1>

<h2 class="key-title">MmioWhitelist</h2>

This section is allowing spaces to be passthrough to macOS that are generally ignored, useful when paired with DevirtualiseMmio.

Placeholder Text instructing user about troubleshooting MmioWhitelist.

<h2 class="key-title">Patch</h2>

This contains general patches, for us, we can ignore this.

<h2 class="key-title">Quirks</h2>

Placeholder Text instructing user what to set.

| Quirk  | Value | Description | 
| ----- | ----- | ----- |
| AllowRelocationBlock | False | Placeholder Reason |
| AvoidRuntimeDefrag | False | Placeholder Reason |
| DevirtualiseMmio | False | Placeholder Reason |
| DisableSingleUser | False | Placeholder Reason |
| DisableVariableWrite | False | Placeholder Reason |
| DiscardHibernateMap | False | Placeholder Reason |
| EnableSafeModeSlide | False | Placeholder Reason |
| EnableWriteUnprotector | False | Placeholder Reason |
| FixupAppleEfiImages | False | Placeholder Reason |
| ForceBooterSignature | False | Placeholder Reason |
| ForceExitBootServices | False | Placeholder Reason |
| ProtectMemoryRegions | False | Placeholder Reason |
| ProtectSecureBoot | False | Placeholder Reason |
| ProtectUefiServices | False | Placeholder Reason |
| ProvideCustomSlide | False | Placeholder Reason |
| ProvideMaxSlide | False | Placeholder Reason |
| RebuildAppleMemoryMap | False | Placeholder Reason |
| ResizeAppleGpuBars | False | Placeholder Reason |
| SetupVirtualMap | False | Placeholder Reason |
| SignalAppleOS | False | Placeholder Reason |
| SyncRuntimePermissions | False | Placeholder Reason |

<h2 align="center">
  <br>
  <div class="navigation-container">
    <a class="nav-button" href="../02-ACPI/">&larr; Back Page</a>
    <a class="nav-button" href="../04-DeviceProperties/">Next Page &rarr;</a>
  </div>
  <br>
</h2>
