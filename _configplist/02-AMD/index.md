---
layout: default
title: AMD CPUs
nav_order: 3
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

  .desktop-next-button-container {
    text-align: right;
  }

  .desktop-next-button {
    margin: 10px;
    top: 0px;
    bottom: 0px;
    left: 0px;
    right: 0px;
  }
</style>

<p align="center">
  <img width="650" height="200" src="../../../assets/Header-Vendor-AMD.png">
</p>

<h2 align="center">Placeholder Information</h2>

<h4 align="center">This page is a stub, but this page should:</h4>
<br>

1. Help the user select the closest model to their CPU and/or Device description.

2. Take the user to either a Desktop or Laptop/Mobile section.

## Before we start platform-specific configurations
Maybe you've already noticed that there isn't a single Mac with an AMD CPU. Therefore you have to patch the kernel. To do this, we use another tool from CorpNewt.

[AMDVanillaPatches](https://github.com/corpnewt/AMDVanillaPatches/) allows us to merge the required kernel patches without problems. It's pretty self-explanatory. However, you should read the ReadMe of the [kernel patches](https://github.com/AMD-OSX/AMD_Vanilla) to understand what is actually happening. 
First of all, we have to get the tool itself. We can simply download the main branch or clone the repository.

<div style="text-align: center;" markdown="1">
  [![AMDVanillaPatchesRepository](/assets/KernelPatches/AMDVanillaPatchesRepo.png)](/assets/KernelPatches/AMDVanillaPatchesRepo.png)
</div>

Once we have the repository (you may need to unzip it), we should see the following files.

<div style="text-align: center;" markdown="1">
  [![AMDVanillaPatchesRepository](/assets/KernelPatches/AMDVanillaPatchesRepoFiles.png)](/assets/KernelPatches/AMDVanillaPatchesRepoFiles.png)
</div>

You can now choose the appropriate script depending on your platform (Windows users should choose the ``.bat`` file).

We should now be greeted something like this.

<div style="text-align: center;" markdown="1">
  [![AMDVanillaPatchesRepository](/assets/KernelPatches/AMDVanillaPatches.command.png)](/assets/KernelPatches/AMDVanillaPatches.command.png)
</div>

First we want to select option 1). We then choose option 2) and drag and drop our config.plist into it. We then confirm it with enter. 
After that we choose option 3) - Here we have to enter the number of CPU cores of our target system (**NOT** threads).

<div style="text-align: center;" markdown="1">
  <[![AMDVanillaPatchesRepository](/assets/KernelPatches/CPUCores.png)](/assets/KernelPatches/CPUCores.png)
</div>

Now we can close the program and continue with the platform-specific configuration.

<h2 align="center">To begin, select your hardware type:</h2>
<br>

<h2 align="center">
  <br>
  <div class="desktop-next-button-container">
  <a class="desktop-next-button" href="../01-Desktop/index/">Desktop &rarr;</a>
  </div>
  <div class="navigation-container">
    <a class="nav-button" href="../../01-Introduction/index/">&larr; Back Page</a>
    <a class="nav-button" href="../02-Mobile/index/">Laptop/Mobile &rarr;</a>
  </div>
  <br>
</h2>
