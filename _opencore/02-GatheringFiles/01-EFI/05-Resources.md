---
layout: default
title: Resources
parent: EFI Setup
grand_parent: Gathering Files
description: 
nav_order: 5
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

  .image-container {
    display: flex;
    justify-content: space-around;
    align-items: center;
    margin: 20px 0;
  }

  .image-item {
    text-align: center;
    max-width: 300px;
    margin: 0 10px;
  }

  .image-item img {
    max-width: 100%;
    height: auto;
  }
</style>

<p align="center">
  <img width="650" height="200" src="../../../../assets/Headers/Header-OpenCore-Resources.png">
</p>

<h2 align="center">Files used by OpenCanopy</h2>
<br>

This section is here for completeness. **When you intend to configure OpenCanopy, you may return to this page.**

The rest of this page serves as an explanation of how to install themes. **You may now skip it.**

<h2 align="center">
  <br>
  <div class="navigation-container">
    <a class="nav-button" href="../04-Tools/">&larr; Back Page</a>
    <a class="nav-button" href="../../02-PlatformSpecific/index/">Next Page &rarr;</a>
  </div>
  <br>
</h2>
<br>

# **Common Themes**

{: .note }
You can click on an image to expand it! It will open on a new tab.

The following are standard themes that can be downloaded by Acidanthera:

<div class="image-container">
  <div class="image-item">
    <h3>Syrah (Default)</h3>
    <a href="../../../../assets/Dortania/gui.a10019ae.png" target="_blank">
      <img src="../../../../assets/Dortania/gui.a10019ae.png" alt="Syrah (Default)">
    </a>
  </div>
  <div class="image-item">
    <h3>GoldenGate (Modern)</h3>
    <a href="../../../../assets/Dortania/gui-nouveau.8ad4a7b4.png" target="_blank">
      <img src="../../../../assets/Dortania/gui-nouveau.8ad4a7b4.png" alt="GoldenGate (Modern)">
    </a>
  </div>
  <div class="image-item">
    <h3>Chardonnay (Old)</h3>
    <a href="../../../../assets/Dortania/gui-old.53c75c16.png" target="_blank">
      <img src="../../../../assets/Dortania/gui-old.53c75c16.png" alt="Chardonnay (Old)">
    </a>
  </div>
</div>

To install these themes, visit the [OcBinaryData](https://github.com/acidanthera/OcBinaryData) and download it as a ZIP. This will provide you with the 3 default themes for Resources.

Unpack the following data into your own EFI's ``Resources`` folder.

## **Installing third-party themes**

{: .internalnote }
TODO: Add a chart of known third party themes, and instruct a user on dropping it into Resources, how to properly have them foldered.

## **Configuring config.plist**

It's time to configure OpenCore to know what theme to use, along with other proper settings required.

Edit the following keys with ProperTree under:

```
-> Misc 
  -> Boot
```

| Key | Type | Value |
| PickerAttributes | Number | 17 |
| PickerMode | String | External |
| PickerVariant | String | Acidanthera\GoldenGate |

Other valid strings that are accepted by PickerVariant with the Common themes are:

| Value | Effect |
| Auto | Automatically select one set of icons based on DefaultBackground colour. |
| Acidanthera\Syrah | The Syrah (Default) theme. |
| Acidanthera\GoldenGate | The Nouveau (GoldenGate/Modern) theme. |
| Acidanthera\Chardonnay | The Vintage (Chardonnay/Old) theme. |

Ensure you have ``OpenCanopy.efi``, so you can OC Snapshot.

# **Boot Chime**

{: .internalnote }
TODO: Add information on creating a boot chime audio, and adding it to Resources, as well as installing the standard Boot Chime sound.

## **Configuring config.plist**

{: .internalnote }
TODO: Add information on setting boot chime audio in config.plist for OpenCore

<h2 align="center">
  <br>
  <div>
    <a class="top-button" href="#">&uarr; Go to the Top &uarr;</a>
  </div>
  <br>
</h2>
