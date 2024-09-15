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
  <img width="650" height="200" src="../../assets/Header-Placeholder.png">
</p>

<h2 align="center">Placeholder Information</h2>

<h4 align="center">This page is a stub, but this page should:</h4>
<br>

1. Explain how this section is broken up
2. Explain how to read the pages, such as ACPI, Booter, Kernel

## Before you start with the configuration

Before we dive into configuring our plist, we should clarify a few things. A .plist file is not compiled - it is readable and editable for us. In order to make changes, we have to somehow introduce them to the file.
In theory, you can use any program you can edit a text with, but if you don't want to waste years in Microsoft Word, Nano or TextEdit, it is advisable to use a adequate plist editor. 

For beginners, it's recommended to use [CorpNewt's](https://github.com/corpnewt) [ProperTree](https://github.com/corpnewt/ProperTree) for various reasons. ProperTree is a versatile, free plist editor that works across multiple platforms. Since it’s built with Python, it can theoretically run on any system that supports Python. One of its standout features is the array of built-in functions specifically designed for OpenCore, making it highly convenient. In contrast, using other editors would require you to access these functions separately or doing everything by hand.
However, you are free to use whatever you want.

{: .note }
Due to a bug inside Xcode that periodically trims your plist, it's not recommend to use it.

{: .warning }
Do **NOT** use configurators. Every conceivable reason, apart from laziness, speaks against it. Configurators are not recommended as they make assumptions, have no kext load order logic, make changes without telling you, often auto-save on opening your config (which bakes in those changes they didn't tell you they were making), and make it easier to make mistakes. Configurations teach you nothing, they are loaded with bugs and corrupt your plist.

Now that we know what we can use and what we shouldn't use (!), we can make the first changes to our config.plist.

## Taking a snapshot
CorpNewts [OCSnapshot](https://github.com/corpnewt/OCSnapshot) is able to transfer the structure of your EFI folder into your config.plist. The OCSnapshot function is already integrated in ProperTree. All you have to do is open ProperTree, press ``Ctrl+R`` (or ``Cmd+R``) and select the ``OC`` folder. However, when you take a snapshot for the first time, it is highly recommended to take a so-called "clean snapshot". To do this, press ``Ctrl/Cmd+Shift+R`` and select the ``OC`` folder.

Explained in more detail:
**OC Snapshot** updates the current values in ``ACPI -> Add``, ``Kernel -> Add``, ``Misc -> Tools``, and ``UEFI -> Drivers`` by only adding or removing entries as needed. **OC Clean Snapshot** clears these four sections completely and adds all entries from scratch.

Both functions check kext load order and fix common user errors, but **OC Snapshot** keeps your custom settings for existing entries like Enabled, MinKernel, MaxKernel, and Comments.

{: .headsup }
Attention! Every time you change the structure of your folder, e.g. add or remove a kext, SSDT or tool, you must repeat this step.

<br>
<h4 align="center">We now present the nav bar:</h4>

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
