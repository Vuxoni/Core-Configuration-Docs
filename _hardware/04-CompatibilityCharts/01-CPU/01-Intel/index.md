---
layout: default
title: Intel
parent: CPU Support Chart
grand_parent: Compatibility Charts
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

  .toc-button {
    margin: 10px;
    align: center;
  }

  .top-button {
    margin: 10px;
    align: center;
  }

  .bottom-button {
    margin: 10px;
    align: center;
  }
</style>

<p align="center">
  <img width="650" height="200" src="../../../../../assets/Headers/Header-IntelBased.png">
</p>

{: .internalnote }
We need to pick through and remove non viable CPUs that would not make a working system combination, for example, there are some Laptop CPUs that do not make sense to have on this list, as the iGPU is not supported, thus they would not be able to technically use OS X / macOS in any reasonable way.

{: .note }
> When it comes to Intel CPUs, the vast majority are supported. Whether you are on a Desktop or Laptop, will determine the viablity of your system. Even if your iGPU is not supported, on Desktop you can still utilize a dedicated Graphics Card to resolve incompatibilities.
>
> You may find that your CPU does not exceed a specific OS X / macOS release, this is mainly due to two factors that can be reason: Missing CPU instructions required for modern macOS, or, an 11th Gen CPU or newer. When you are missing CPU instructions, it means your CPU is too old to utilize typically, AX2 but can also be in regards to missing SSSE4.2 which is required on modern macOS. **For those who have a CPU newer than 10th Gen, your CPU does not have a supported iGPU and will require you to use a dedicated graphics card.**
>
> We are aware that OpenCore Legacy Patcher can be used, but due to the fact that it is patching the Root system itself to bring back kernel extensions (and the fact that OCLP does not officially support Hacs), you will find that support channels will not assist with OCLP. The software is intended for real Mac machines who have been limited to lower macOS releases because of their iGPUs being dropped, such as MacBookAir7,2 which cannot exceed Monterey (12).
>
> The "F" variants of Intel CPUs lack integrated graphics, requiring a dedicated graphics card for display output. In contrast, the "K" and "KF" models are unlocked for overclocking. Additionally, "T" variants are designed for lower power consumption and thermal output, making them suitable for energy-efficient systems. Meanwhile, "G" variants come with integrated graphics, often intended for systems that do not require a separate GPU. Each of these suffixes helps to indicate the specific capabilities and intended use cases of the processors without lots of research.

<h2 align="center">Quick Navigation</h2>

<h2 align="center">
  <br>
  <div>
    <a class="toc-button" href="#desktop">&darr; Go to Desktop CPUs &darr;</a>
    <a class="toc-button" href="#laptop">&darr; Go to Laptop CPUs &darr;</a>
    <br>
    <br>
    <a class="bottom-button" href="#-">&darr; Go to Bottom &darr;</a>
  </div>
  <br>
</h2>

# Desktop

## Raptor Lake and Raptor Lake Refresh (13th / 14th Generation Core i Branding)

| Name | Initial Support | Latest Support | Notes |
| --- | --- | --- | --- |
| Core i9 14900KF | Placeholder (XX) | Placeholder (XX) | Requires a dGPU |
| Core i9 14900K | Placeholder (XX) | Placeholder (XX) | Requires a dGPU |
| Core i9 14900 | Placeholder (XX) | Placeholder (XX) | Requires a dGPU |
| Core i7 14700KF | Placeholder (XX) | Placeholder (XX) | Requires a dGPU |
| Core i7 14700K | Placeholder (XX) | Placeholder (XX) | Requires a dGPU |
| Core i7 14700 | Placeholder (XX) | Placeholder (XX) | Requires a dGPU |
| Core i5 14600K | Placeholder (XX) | Placeholder (XX) | Requires a dGPU |
| Core i5 14600K | Placeholder (XX) | Placeholder (XX) | Requires a dGPU |
| Core i5 14600 | Placeholder (XX) | Placeholder (XX) | Requires a dGPU |
| Core i5 14500 | Placeholder (XX) | Placeholder (XX) | Requires a dGPU |
| Core i5 14400F | Placeholder (XX) | Placeholder (XX) | Requires a dGPU |
| Core i5 14400 | Placeholder (XX) | Placeholder (XX) | Requires a dGPU |
| Core i3 14100F | Placeholder (XX) | Placeholder (XX) | Requires a dGPU |
| Core i3 14100 | Placeholder (XX) | Placeholder (XX) | Requires a dGPU |
| Core i9 13900KS | Placeholder (XX) | Placeholder (XX) | Requires a dGPU |
| Core i9 13900KF | Placeholder (XX) | Placeholder (XX) | Requires a dGPU |
| Core i9 13900K | Placeholder (XX) | Placeholder (XX) | Requires a dGPU |
| Core i9 13900F | Placeholder (XX) | Placeholder (XX) | Requires a dGPU |
| Core i9 13900 | Placeholder (XX) | Placeholder (XX) | Requires a dGPU |
| Core i7 13700KF | Placeholder (XX) | Placeholder (XX) | Requires a dGPU |
| Core i7 13700K | Placeholder (XX) | Placeholder (XX) | Requires a dGPU |
| Core i7 13700F | Placeholder (XX) | Placeholder (XX) | Requires a dGPU |
| Core i7 13700 | Placeholder (XX) | Placeholder (XX) | Requires a dGPU |
| Core i5 13600KF | Placeholder (XX) | Placeholder (XX) | Requires a dGPU |
| Core i5 13600K | Placeholder (XX) | Placeholder (XX) | Requires a dGPU |
| Core i5 13600 | Placeholder (XX) | Placeholder (XX) | Requires a dGPU |
| Core i5 13500 | Placeholder (XX) | Placeholder (XX) | Requires a dGPU |
| Core i5 13400F | Placeholder (XX) | Placeholder (XX) | Requires a dGPU |
| Core i5 13400 | Placeholder (XX) | Placeholder (XX) | Requires a dGPU |
| Core i3 13100F | Placeholder (XX) | Placeholder (XX) | Requires a dGPU |
| Core i3 13100 | Placeholder (XX) | Placeholder (XX) | Requires a dGPU |

## Alder Lake (12th Generation Core i Branding)

| Name | Initial Support | Latest Support | Notes |
| --- | --- | --- | --- |
| Core i9 12900KS | Placeholder (XX) | Placeholder (XX) | Requires a dGPU |
| Core i9 12900KF | Placeholder (XX) | Placeholder (XX) | Requires a dGPU |
| Core i9 12900K | Placeholder (XX) | Placeholder (XX) | Requires a dGPU |
| Core i9 12900F | Placeholder (XX) | Placeholder (XX) | Requires a dGPU |
| Core i9 12900 | Placeholder (XX) | Placeholder (XX) | Requires a dGPU |
| Core i7 12700KF | Placeholder (XX) | Placeholder (XX) | Requires a dGPU |
| Core i7 12700K | Placeholder (XX) | Placeholder (XX) | Requires a dGPU |
| Core i7 12700F | Placeholder (XX) | Placeholder (XX) | Requires a dGPU |
| Core i7 12700 | Placeholder (XX) | Placeholder (XX) | Requires a dGPU |
| Core i5 12600KF | Placeholder (XX) | Placeholder (XX) | Requires a dGPU |
| Core i5 12600K | Placeholder (XX) | Placeholder (XX) | Requires a dGPU |
| Core i5 12600 | Placeholder (XX) | Placeholder (XX) | Requires a dGPU |
| Core i5 12500 | Placeholder (XX) | Placeholder (XX) | Requires a dGPU |
| Core i5 12400F | Placeholder (XX) | Placeholder (XX) | Requires a dGPU |
| Core i5 12400 | Placeholder (XX) | Placeholder (XX) | Requires a dGPU |
| Core i3 12100F | Placeholder (XX) | Placeholder (XX) | Requires a dGPU |
| Core i3 12100T | Placeholder (XX) | Placeholder (XX) | Requires a dGPU |
| Core i3 12100 | Placeholder (XX) | Placeholder (XX) | Requires a dGPU |

## Rocket Lake (11th Generation Core i Branding)

{: .internalnote }
This section was horrible, and may be wrong and may be missing lots of other variants...

| Name | Initial Support | Latest Support | Notes |
| --- | --- | --- | --- |
| Core i9 11900T | Placeholder (XX) | Placeholder (XX) | Requires a dGPU |
| Core i9 11900KF | Placeholder (XX) | Placeholder (XX) | Requires a dGPU |
| Core i9 11900K | Placeholder (XX) | Placeholder (XX) | Requires a dGPU |
| Core i9 11900F | Placeholder (XX) | Placeholder (XX) | Requires a dGPU |
| Core i9 11900 | Placeholder (XX) | Placeholder (XX) | Requires a dGPU |
| Core i7 11700T | Placeholder (XX) | Placeholder (XX) | Requires a dGPU |
| Core i7 11700KF | Placeholder (XX) | Placeholder (XX) | Requires a dGPU |
| Core i7 11700K | Placeholder (XX) | Placeholder (XX) | Requires a dGPU |
| Core i7 11700F | Placeholder (XX) | Placeholder (XX) | Requires a dGPU |
| Core i7 11700 | Placeholder (XX) | Placeholder (XX) | Requires a dGPU |
| Core i5 11600T | Placeholder (XX) | Placeholder (XX) | Requires a dGPU |
| Core i5 11600KF | Placeholder (XX) | Placeholder (XX) | Requires a dGPU |
| Core i5 11600K | Placeholder (XX) | Placeholder (XX) | Requires a dGPU |
| Core i5 11600 | Placeholder (XX) | Placeholder (XX) | Requires a dGPU |
| Core i5 11500T | Placeholder (XX) | Placeholder (XX) | Requires a dGPU |
| Core i5 11500 | Placeholder (XX) | Placeholder (XX) | Requires a dGPU |
| Core i5 11400T | Placeholder (XX) | Placeholder (XX) | Requires a dGPU |
| Core i5 11400F | Placeholder (XX) | Placeholder (XX) | Requires a dGPU |
| Core i5 11400 | Placeholder (XX) | Placeholder (XX) | Requires a dGPU |
| Core i3 11320H | Placeholder (XX) | Placeholder (XX) | Requires a dGPU |
| Core i3 11300H | Placeholder (XX) | Placeholder (XX) | Requires a dGPU |
| Core i3 11200 | Placeholder (XX) | Placeholder (XX) | Requires a dGPU |
| Core i3 11100B | Placeholder (XX) | Placeholder (XX) | Requires a dGPU |
| Core i3 11100HE | Placeholder (XX) | Placeholder (XX) | Requires a dGPU |

## Comet Lake (10th Generation Core i Branding)

{: .note }
This is the final CPU generation with supported iGPUs if you lack a dedicated Graphics card.

| Name | Initial Support | Latest Support | Notes |
| --- | --- | --- | --- |
| Core i5 10600T | Placeholder (XX) | Placeholder (XX) | Intel® UHD Graphics 630 |
| Core i5 10600KF | Placeholder (XX) | Placeholder (XX) | Requires a dGPU |
| Core i5 10600K | Placeholder (XX) | Placeholder (XX) | Intel® UHD Graphics 630 |
| Core i5 10600 | Placeholder (XX) | Placeholder (XX) | Intel® UHD Graphics 630 |
| Core i5 10500T | Placeholder (XX) | Placeholder (XX) | Intel® UHD Graphics 630 |
| Core i5 10500 | Placeholder (XX) | Placeholder (XX) | Intel® UHD Graphics 630 |
| Core i5 10400T | Placeholder (XX) | Placeholder (XX) | Intel® UHD Graphics 630 |
| Core i5 10400F | Placeholder (XX) | Placeholder (XX) | Requires a dGPU |
| Core i5 10400 | Placeholder (XX) | Placeholder (XX) | Intel® UHD Graphics 630 |
| Core i3 10320 | Placeholder (XX) | Placeholder (XX) | Intel® UHD Graphics 630 |
| Core i3 10300T | Placeholder (XX) | Placeholder (XX) | Intel® UHD Graphics 630 |
| Core i3 10300 | Placeholder (XX) | Placeholder (XX) | Intel® UHD Graphics 630 |
| Core i3 10105F | Placeholder (XX) | Placeholder (XX) | Requires a dGPU |
| Core i3 10105 | Placeholder (XX) | Placeholder (XX) | Intel® UHD Graphics 630 |
| Core i3 10100T | Placeholder (XX) | Placeholder (XX) | Intel® UHD Graphics 630 |
| Core i3 10100F | Placeholder (XX) | Placeholder (XX) | Requires a dGPU |
| Core i3 10100 | Placeholder (XX) | Placeholder (XX) | Intel® UHD Graphics 630 |

## Coffee Lake and Coffee Lake Refresh (8th / 9th Generation Core i Branding)

| Name | Initial Support | Latest Support | Notes |
| --- | --- | --- | --- |
| Core i9 9900K | Placeholder (XX) | Placeholder (XX) | Intel® UHD Graphics 630 |
| Core i9 9900KF | Placeholder (XX) | Placeholder (XX) | Requires a dGPU |
| Core i9 9900 | Placeholder (XX) | Placeholder (XX) | Intel® UHD Graphics 630 |
| Core i7 9700K | Placeholder (XX) | Placeholder (XX) | Intel® UHD Graphics 630 |
| Core i7 9700KF | Placeholder (XX) | Placeholder (XX) | Requires a dGPU |
| Core i7 9700 | Placeholder (XX) | Placeholder (XX) | Intel® UHD Graphics 630 |
| Core i5 9600K | Placeholder (XX) | Placeholder (XX) | Intel® UHD Graphics 630 |
| Core i5 9600KF | Placeholder (XX) | Placeholder (XX) | Requires a dGPU |
| Core i5 9600 | Placeholder (XX) | Placeholder (XX) | Intel® UHD Graphics 630 |
| Core i5 9500 | Placeholder (XX) | Placeholder (XX) | Intel® UHD Graphics 630 |
| Core i3 9350K | Placeholder (XX) | Placeholder (XX) | Intel® UHD Graphics 630 |
| Core i3 9300 | Placeholder (XX) | Placeholder (XX) | Intel® UHD Graphics 630 |
| Core i3 9300T | Placeholder (XX) | Placeholder (XX) | Intel® UHD Graphics 630 |
| Core i3 9100 | Placeholder (XX) | Placeholder (XX) | Intel® UHD Graphics 630 |
| Core i3 9100F | Placeholder (XX) | Placeholder (XX) | Requires a dGPU |
| Core i7 8700K | Placeholder (XX) | Placeholder (XX) | Intel® UHD Graphics 630 |
| Core i7 8700 | Placeholder (XX) | Placeholder (XX) | Intel® UHD Graphics 630 |
| Core i7 8700T | Placeholder (XX) | Placeholder (XX) | Intel® UHD Graphics 630 |
| Core i5 8600K | Placeholder (XX) | Placeholder (XX) | Intel® UHD Graphics 630 |
| Core i5 8600 | Placeholder (XX) | Placeholder (XX) | Intel® UHD Graphics 630 |
| Core i5 8400 | Placeholder (XX) | Placeholder (XX) | Intel® UHD Graphics 630 |
| Core i3 8350K | Placeholder (XX) | Placeholder (XX) | Intel® UHD Graphics 630 |
| Core i3 8300 | Placeholder (XX) | Placeholder (XX) | Intel® UHD Graphics 630 |
| Core i3 8100 | Placeholder (XX) | Placeholder (XX) | Intel® UHD Graphics 630 |
| Core i3 8100T | Placeholder (XX) | Placeholder (XX) | Intel® UHD Graphics 630 |

## Kaby Lake (7th Generation Core i Branding)

| Name | Initial Support | Latest Support | Notes |
| --- | --- | --- | --- |
| Core i7 7700K | Placeholder (XX) | Placeholder (XX) | Intel® HD Graphics 630 |
| Core i7 7700 | Placeholder (XX) | Placeholder (XX) | Intel® HD Graphics 630 |
| Core i7 7700T | Placeholder (XX) | Placeholder (XX) | Intel® HD Graphics 630 |
| Core i5 7600K | Placeholder (XX) | Placeholder (XX) | Intel® HD Graphics 630 |
| Core i5 7600 | Placeholder (XX) | Placeholder (XX) | Intel® HD Graphics 630 |
| Core i5 7500 | Placeholder (XX) | Placeholder (XX) | Intel® HD Graphics 630 |
| Core i5 7500T | Placeholder (XX) | Placeholder (XX) | Intel® HD Graphics 630 |
| Core i3 7350K | Placeholder (XX) | Placeholder (XX) | Intel® HD Graphics 630 |
| Core i3 7300 | Placeholder (XX) | Placeholder (XX) | Intel® HD Graphics 630 |
| Core i3 7100 | Placeholder (XX) | Placeholder (XX) | Intel® HD Graphics 630 |
| Core i3 7100T | Placeholder (XX) | Placeholder (XX) | Intel® HD Graphics 630 |

## Skylake (6th Generation Core i Branding)

| Name | Initial Support | Latest Support | Notes |
| --- | --- | --- | --- |
| Core i7 6700K | Placeholder (XX) | Placeholder (XX) | Intel® HD Graphics 530 |
| Core i7 6700 | Placeholder (XX) | Placeholder (XX) | Intel® HD Graphics 530 |
| Core i7 6700T | Placeholder (XX) | Placeholder (XX) | Intel® HD Graphics 530 |
| Core i5 6600K | Placeholder (XX) | Placeholder (XX) | Intel® HD Graphics 530 |
| Core i5 6600 | Placeholder (XX) | Placeholder (XX) | Intel® HD Graphics 530 |
| Core i5 6500 | Placeholder (XX) | Placeholder (XX) | Intel® HD Graphics 530 |
| Core i3 6300 | Placeholder (XX) | Placeholder (XX) | Intel® HD Graphics 530 |
| Core i3 6100 | Placeholder (XX) | Placeholder (XX) | Intel® HD Graphics 530 |
| Core i3 6100T | Placeholder (XX) | Placeholder (XX) | Intel® HD Graphics 530 |

## Broadwell (5th Generation Core i Branding)

| Name | Initial Support | Latest Support | Notes |
| --- | --- | --- | --- |
| Core i7 5775R | Placeholder (XX) | Placeholder (XX) | Intel® Iris® Pro Graphics 6200 |
| Core i7 5775C | Placeholder (XX) | Placeholder (XX) | Intel® Iris® Pro Graphics 6200 |
| Core i5 5675R | Placeholder (XX) | Placeholder (XX) | Intel® Iris® Pro Graphics 6200 |
| Core i5 5675C | Placeholder (XX) | Placeholder (XX) | Intel® Iris® Pro Graphics 6200 |
| Core i5 5575R | Placeholder (XX) | Placeholder (XX) | Intel® Iris® Pro Graphics 6200 |

## Haswell (4th Generation Core i Branding)

| Name | Initial Support | Latest Support | Notes |
| --- | --- | --- | --- |
| Core i7 4790K | Placeholder (XX) | Placeholder (XX) | Intel® HD Graphics 4600 |
| Core i7 4790 | Placeholder (XX) | Placeholder (XX) | Intel® HD Graphics 4600 |
| Core i7 4770K | Placeholder (XX) | Placeholder (XX) | Intel® HD Graphics 4600 |
| Core i7 4770 | Placeholder (XX) | Placeholder (XX) | Intel® HD Graphics 4600 |
| Core i5 4690K | Placeholder (XX) | Placeholder (XX) | Intel® HD Graphics 4600 |
| Core i5 4690 | Placeholder (XX) | Placeholder (XX) | Intel® HD Graphics 4600 |
| Core i5 4670K | Placeholder (XX) | Placeholder (XX) | Intel® HD Graphics 4600 |
| Core i5 4670 | Placeholder (XX) | Placeholder (XX) | Intel® HD Graphics 4600 |
| Core i3 4360 | Placeholder (XX) | Placeholder (XX) | Intel® HD Graphics 4600 |
| Core i3 4360T | Placeholder (XX) | Placeholder (XX) | Intel® HD Graphics 4600 |
| Core i3 4350 | Placeholder (XX) | Placeholder (XX) | Intel® HD Graphics 4600 |
| Core i3 4350T | Placeholder (XX) | Placeholder (XX) | Intel® HD Graphics 4600 |
| Core i3 4330 | Placeholder (XX) | Placeholder (XX) | Intel® HD Graphics 4600 |
| Core i3 4130 | Placeholder (XX) | Placeholder (XX) | Intel® HD Graphics 4400 |

## Ivy Bridge (3rd Generation Core i Branding)

| Name | Initial Support | Latest Support | Notes |
| --- | --- | --- | --- |
| Core i7 3770K | Placeholder (XX) | Placeholder (XX) | Intel® HD Graphics 4000 |
| Core i7 3770 | Placeholder (XX) | Placeholder (XX) | Intel® HD Graphics 4000 |
| Core i5 3570K | Placeholder (XX) | Placeholder (XX) | Intel® HD Graphics 2500 |
| Core i5 3570 | Placeholder (XX) | Placeholder (XX) | Intel® HD Graphics 2500 |
| Core i5 3550 | Placeholder (XX) | Placeholder (XX) | Intel® HD Graphics 2500 |
| Core i3 3240 | Placeholder (XX) | Placeholder (XX) | Intel® HD Graphics 2500 |
| Core i3 3240T | Placeholder (XX) | Placeholder (XX) | Intel® HD Graphics 2500 |
| Core i3 3220 | Placeholder (XX) | Placeholder (XX) | Intel® HD Graphics 2500 |
| Core i3 3210 | Placeholder (XX) | Placeholder (XX) | Intel® HD Graphics 2500 |

## Sandy Bridge (2nd Generation Core i Branding)

| Name | Initial Support | Latest Support | Notes |
| --- | --- | --- | --- |
| Core i7 2700K | Placeholder (XX) | Placeholder (XX) | Requires a dGPU |
| Core i7 2600K | Placeholder (XX) | Placeholder (XX) | Requires a dGPU |
| Core i7 2600 | Placeholder (XX) | Placeholder (XX) | Requires a dGPU |
| Core i7 2500K | Placeholder (XX) | Placeholder (XX) | Requires a dGPU |
| Core i7 2500 | Placeholder (XX) | Placeholder (XX) | Requires a dGPU |
| Core i5 2500K | Placeholder (XX) | Placeholder (XX) | Requires a dGPU |
| Core i5 2500 | Placeholder (XX) | Placeholder (XX) | Requires a dGPU |
| Core i5 2400 | Placeholder (XX) | Placeholder (XX) | Requires a dGPU |
| Core i3 2130 | Placeholder (XX) | Placeholder (XX) | Requires a dGPU |
| Core i3 2120 | Placeholder (XX) | Placeholder (XX) | Requires a dGPU |
| Core i3 2120T | Placeholder (XX) | Placeholder (XX) | Requires a dGPU |
| Core i3 2100 | Placeholder (XX) | Placeholder (XX) | Requires a dGPU |
| Pentium G850 | Placeholder (XX) | Placeholder (XX) | Requires a dGPU |
| Pentium G860 | Placeholder (XX) | Placeholder (XX) | Requires a dGPU |
| Pentium G840 | Placeholder (XX) | Placeholder (XX) | Requires a dGPU |

## Nelahem, Lynnfield, Bloomfield (1st Generation Core i Branding)

| Name | Initial Support | Latest Support | Notes |
| --- | --- | --- | --- |
| Core i7 975 | Placeholder (XX) | Placeholder (XX) | Requires a dGPU |
| Core i7 960 | Placeholder (XX) | Placeholder (XX) | Requires a dGPU |
| Core i7 940 | Placeholder (XX) | Placeholder (XX) | Requires a dGPU |
| Core i7 920 | Placeholder (XX) | Placeholder (XX) | Requires a dGPU |
| Core i7 870 | Placeholder (XX) | Placeholder (XX) | Requires a dGPU |
| Core i7 870S | Placeholder (XX) | Placeholder (XX) | Requires a dGPU |
| Core i7 860S | Placeholder (XX) | Placeholder (XX) | Requires a dGPU |
| Core i7 860 | Placeholder (XX) | Placeholder (XX) | Requires a dGPU |
| Core i5 760 | Placeholder (XX) | Placeholder (XX) | Requires a dGPU |
| Core i5 750 | Placeholder (XX) | Placeholder (XX) | Requires a dGPU |

{: .internalnote }
I, don't even know how to classify all of these, not an Intel user at all, but I want to cover older legacy OS X such as Tiger, Leopard, and Snow Leopard.

## Wolfdale (4th Generation Core 2)

| Name | Initial Support | Latest Support | Notes |
| --- | --- | --- | --- |
| Core 2 XXX XXXX | Placeholder (XX) | Placeholder (XX) | Requires a dGPU |

## Penryn (3rd Generation Core 2)

| Name | Initial Support | Latest Support | Notes |
| --- | --- | --- | --- |
| Core 2 XXX XXXX | Placeholder (XX) | Placeholder (XX) | Requires a dGPU |

## Conroe, Yorkfield (2nd Generation Core 2)

| Name | Initial Support | Latest Support | Notes |
| --- | --- | --- | --- |
| Core 2 XXX XXXX | Placeholder (XX) | Placeholder (XX) | Requires a dGPU |

## Yonah (1st Generation Core 2)

| Name | Initial Support | Latest Support | Notes |
| --- | --- | --- | --- |
| Core 2 XXX XXXX | Placeholder (XX) | Placeholder (XX) | Requires a dGPU |

<h2 align="center">
  <br>
  <div>
    <a class="top-button" href="#">&uarr; Go to Top &uarr;</a>
    <a class="bottom-button" href="#-">&darr; Go to Bottom &darr;</a>
  </div>
  <br>
</h2>

# Laptop

{: .internalnote }
As if I wasn't already bad with Intel CPUs, I don't even want to bother with Laptop variants right now. A todo for later, or if someone wants to do this, then tyvm.

## Raptor Lake (13th Generation Core i Branding)

| Name | Initial Support | Latest Support | Notes |
| --- | --- | --- | --- |
| Core iX XXXX | Placeholder (XX) | Placeholder (XX) | Placeholder |

<br>
<a id="-"></a>
<h2 align="center">
  <br>
  <div class="navigation-container">
    <a class="nav-button" href="../../../01-CPU/index">&larr; Back Page</a>
    <a class="nav-button" href="../../../02-GPU/index">Next Page &rarr;</a>
  </div>
  <br>
</h2>
