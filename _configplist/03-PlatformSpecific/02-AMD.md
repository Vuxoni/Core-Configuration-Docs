---
layout: default
title: AMD
parent: Platform Specific
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

  .top-button {
    margin: 10px;
    align: center;
  }
</style>

<p align="center">
  <img width="650" height="200" src="../../../assets/Headers/Header-Vendor-AMD.png">
</p>

{: .internalnote }
This page is in progress, the intention is to eventually have a ToC at the bottom before the navbar, that can quickly display all of our AMD specific configurations.

This page serves as a way to document further potential platform specific changes required to ``config.plist`` according to whatever circumstances require it.

Unfortunately, as you may be aware, no Mac has ever released with an AMD CPU. Therefore we must patch the kernel to natively (and most importantly, vanilla) boot on AMD CPUs without various checks and functions leading to kernel panics, and without relying on a custom built kernel. 

This step is not skippable by anyone on an AMD CPU regardless of generation, and the rest of the Platform Specific changes are below this one as they are optional/conditionally dependent on your target hardware specifically.

To do this, we use another tool from [CorpNewt](https://github.com/CorpNewt) named [AMDVanillaPatches](https://github.com/corpnewt/AMDVanillaPatches/) which allows us to merge the required kernel patches with less manual editing.

Although this section has been made simple with the mentioned tool above, it is important to take time to read the README of the [AMD Vanilla Patches](https://github.com/AMD-OSX/AMD_Vanilla) repository which provides detailed information on the manual process, and is the home of the patches we will use.

To get the tool itself, we can simply download the main branch or clone the repository via CLI.

<div style="text-align: center;" markdown="1">
  [![AMDVanillaPatchesRepository](/assets/KernelPatches/AMDVanillaPatchesRepo.png)](/assets/KernelPatches/AMDVanillaPatchesRepo.png)
</div>

Once we have the repository (you may need to unzip it), we should see the following files:

<div style="text-align: center;" markdown="1">
  [![AMDVanillaPatchesRepository](/assets/KernelPatches/AMDVanillaPatchesRepoFiles.png)](/assets/KernelPatches/AMDVanillaPatchesRepoFiles.png)
</div>

You can now choose the appropriate script depending on your platform. Windows users should choose the ``.bat`` file.

We should now be greeted with a terminal similar to this (subject to change with updates):

<div style="text-align: center;" markdown="1">
  [![AMDVanillaPatchesRepository](/assets/KernelPatches/AMDVanillaPatches.command.png)](/assets/KernelPatches/AMDVanillaPatches.command.png)
</div>

First we want to select ``Install/Update vanilla patches``.

We then choose ``Select target config.plist`` to drag and drop our config.plist in to the terminal window. This will paste the file path in the prompt. 

We then confirm with enter, if the path is correct.

We will now be brought back to the main menu, this time with the above details showing our selected configuration plist, and the version of the Patches.

<div style="text-align: center;" markdown="1">
  [![Display Main Menu 2](/assets/KernelPatches/)](/assets/KernelPatches/)
</div>

After all of the setup is complete, we choose ``Patch target config.plist``

Here we have to enter the number of CPU Cores of our target system (**NOT** Threads).

<div style="text-align: center;" markdown="1">
  [![AMDVanillaPatchesRepository](/assets/KernelPatches/CPUCores.png)](/assets/KernelPatches/CPUCores.png)
</div>

Once you've entered the value and pressed enter, you should be ready as it will push these changes to your configuration file.

Now we can close the program and continue with the platform-specific configurations, please scroll to the very bottom to ensure you covered all potentially applicable AMD specific configurations.

<h2 align="center">
  <br>
  <div class="navigation-container">
    <a class="nav-button" href="../index/">&larr; Back Page</a>
    <a class="nav-button" href="">Next Page &rarr;</a>
  </div>
  <br>
</h2>

<hr>

## **Example Entry**

{: .internalnote }
This is an example entry

<hr>

## **Example Entry 2**

{: .internalnote }
This is an example entry, notice this is the last entry, it does not have a horizontal line.

<h2 align="center">
  <br>
  <div>
    <a class="top-button" href="#">&uarr; Go to the Top &uarr;</a>
  </div>
  <br>
</h2>
