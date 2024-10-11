---
layout: default
title: Introduction
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

  .intel-next-button-container {
    text-align: right;
  }

  .intel-next-button {
    margin: 10px;
    top: 0px;
    bottom: 0px;
    left: 0px;
    right: 0px;
  }
</style>

<p align="center">
  <img width="650" height="200" src="../../../assets/Headers/Header-ConfiguringOpenCore.png">
</p>

<h2 align="center">Preliminary Information</h2>
<br>

{: .warning }
Do **NOT** use Configurators. Every conceivable, and technical reason speaks against it. Configurators are not recommended because they do not conform to OpenCore's formatting and data. Other reasons to not use a configurator include: No Kext ordering logic based on dependencies of Kexts, Auto-saving changes without warning (especially damaging changes), Zero'ing out Data that is valid for OpenCore, but invalid by the configurators PLIST parser library, so its deemed to become "0", deleting important data such as AppleECID.

{: .headsup }
Due to a bug with Xcode's plist editor that randomly trims your plist, along with incompatibilities with OpenCore's PLIST formatting it is not recommended for usage.

Before we dive into configuring OpenCore, we should clarify a few things.

The .plist file format is an Apple crafted XML-type document. In theory, you can use any program you can edit plain text with, but if you don't want to waste years in Microsoft Word, Nano or TextEdit, it is advisable to use a adequate plist editor that properly reads the XML tags and displays them in a properly human-editable format.

It's recommended to use [CorpNewt](https://github.com/corpnewt)'s [ProperTree](https://github.com/corpnewt/ProperTree) for various reasons. ProperTree is a versatile, cross-platform PLIST editor that works across Python versions. Since it’s built with Python, it can theoretically run on any system that supports Python 2 or newer. One of its standout features is the array of built-in functions specifically designed for OpenCore, making it highly convenient.

## **Fetching ProperTree**

We can simply download the main branch or clone the repository via CLI.

<div style="text-align: center;" markdown="1">
[![Repository](/assets/ProperTree/ProperTreeRepo.png)](/assets/ProperTree/ProperTreeRepo.png)
</div>

Once we have downloaded ProperTree (and unpacked it if necessary), we will be greeted with the following files.

{: .note }
The difference between ``ProperTree.bat`` and ``ProperTreeQuiet.bat`` is that no console window pops up. If you are annoyed by the console window, you can use the quiet version.

<div style="text-align: center;" markdown="1">
[![Files](/assets/ProperTree/ProperTreeFiles.png)](/assets/ProperTree/ProperTreeFiles.png)
</div>

Windows users should choose the ``.bat`` file.

Mac users should choose the ``.command`` file.

Users on all platforms, including Linux, can also use the ``.py`` file instead by calling it with ``python``.

When you open ProperTree, you will be greeted with the following window:

<div style="text-align: center;" markdown="1">
[![Blank file](/assets/ProperTree/ProperTreeUntitled1.png)](/assets/ProperTree/ProperTreeUntitled1.png)
</div>

Now we want to open our previously renamed ``config.plist`` file on ``USB/EFI/OC/``. From now on we will refer to it simply as the ``plist``.

You can open a select file window by pressing ``Cmd/Ctrl+O`` and selecting the correct file. If you did it correctly, it should look something like this:

{: .note }
You can remove the first 4 warning entries. They don't matter, as they are simply comments.

<div style="text-align: center;" markdown="1">
[![config.plist](/assets/ProperTree/ProperTreePlist.png)](/assets/ProperTree/ProperTreePlist.png)
</div>

## **Taking a Snapshot of your EFI**

{: .important }
Every time you change the structure of your OC folder, e.g. add or remove a kext, SSDT or tool, you must repeat this step. OpenCore is **NOT** aware of the files in your EFI, the config plist is what tells OC what is what, and where is what, and whether or not to load it.

{: .note-title }
> Snapshotting explained in deep detail
>
> **OC Snapshot**
>
> Updates the current values in ``ACPI -> Add``, ``Kernel -> Add``, ``Misc -> Tools``, and ``UEFI -> Drivers`` by only adding or removing entries as needed.
>
> **OC Clean Snapshot**
>
> Clears these four sections completely and adds all entries from scratch.
>
> *Both functions update various sections, but **OC Snapshot** keeps your custom settings for existing entries like Enabled, MinKernel, MaxKernel, and Comments.*

[CorpNewt](https://github.com/corpnewt)'s [OCSnapshot](https://github.com/corpnewt/OCSnapshot) CLI tool is able to transfer the structure of your EFI folder into your config.plist.

The OCSnapshot function is already integrated in ProperTree. 

All you have to do is ensure you're focused on ProperTree, and press ``Ctrl+R`` (or ``Cmd+R``) and select the ``OC`` folder. 

However, when you take a snapshot for the first time, it is highly recommended to take a so-called ``Clean Snapshot``. 

To do this, press ``Ctrl/Cmd+Shift+R`` and select the ``OC`` folder.

<div style="text-align: center;" markdown="1">
  [![config.plist](/assets/ProperTree/ProperTreeSnapshot.png)](/assets/ProperTree/ProperTreeSnapshot.png)
</div>

At this point in the Docs, you should now do an ``Clean OC Snapshot``, to initialize your plists content.

<h3 align="center">When you are ready to continue, please select your CPU Brand below.</h3>

<h2 align="center">
  <br>
  <div class="intel-next-button-container">
  <a class="intel-next-button" href="../01-Intel/index/">Intel &rarr;</a>
  </div>
  <div class="navigation-container">
    <a class="nav-button" href="../../configfolders/06-Tools/">&larr; Back Page</a>
    <a class="nav-button" href="../02-AMD/index/">AMD &rarr;</a>
  </div>
  <br>
</h2>
