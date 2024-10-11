---
layout: default
title: AMD
parent: CPU Support Chart
grand_parent: Compatibility Charts
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
</style>

<p align="center">
  <img width="650" height="200" src="../../../../../assets/Headers/Header-AMDBased.png">
</p>

{: .note }
AMD chips do not work without problems. Many programs use libraries that AMD CPUs cannot easily handle. Programs affected include, but are not limited to Discord Krisp and Adobe programms. Luckily, theres an easy way around it: <a href="https://github.com/NyaomiDEV/AMDFriend">AMDFriend</a>.

{: .internalnote }
AMD Fusion / FX Chips (and maybe K10) to be added!

# Desktop Chips

| Generation        | Product Name    | Architecture   | Initial Support     | Notes                                                                                     |
| ----------------- | --------------- | -------------- | ------------------- | ----------------------------------------------------------------------------------------- |
| Ryzen 9000 series | Granite Ridge   | Zen 5          | Untested            | Incompatible iGPU                                                                         |
| Ryzen 8000 series | Phoenix         | Zen 4 / Zen 4c | Untested            | Heterogenous core configuration, may result in serious issues. Incompatible iGPU and NPU. |
| Ryzen 7000 series | Raphael         | Zen 4          | High Sierra (10.13) | Incompatible iGPU                                                                         |
| Ryzen 5000 series | Cezanne/Vermeer | Zen 3          | High Sierra (10.13) | "compatible" iGPU (initial support in 10.15)                                              |
| Ryzen 4000 series | Renoir          | Zen 2          | High Sierra (10.13) | "compatible" iGPU (initial support in 10.15)                                              |
| Ryzen 3000 series | Matisse         | Zen 2          | High Sierra (10.13) |                                                                                           |
| Ryzen 3000 series | Picasso         | Zen+           | High Sierra (10.13) | "compatible" iGPU (initial support in 10.15)                                              |
| Ryzen 2000 series | Pinneacle Ridge | Zen+           | High Sierra (10.13) |                                                                                           |
| Ryzen 2000 series | Raven Ridge     | Zen            | High Sierra (10.13) | "compatible" iGPU (initial support in 10.15)                                              |
| Ryzen 1000 series | Pineaccle Ridge | Zen+           | High Sierra (10.13) | only affecting Ryzen 3 1200 AF chips                                                      |
| Ryzen 1000 series | Summit Ridge    | Zen            | High Sierra (10.13) |                                                                                           |

# Laptop Chips
{: .note }
Laptops without a compatible APU are marked as incompatible. You may be able to run macOS with an eGPU or without graphic acceleration though (initial support is depending on your GPU).

| Generation          | Product Name      | Architecture   | Initial Support  | Notes                                                                                     |
| ------------------- | ----------------- | -------------- | ---------------- | ----------------------------------------------------------------------------------------- |
| Ryzen AI 300 series | Strix Point       | Zen 5 / Zen 5c | None             | Heterogenous core configuration, may result in serious issues. Incompatible iGPU and NPU. |
| Ryzen 8000 series   | Hawk Point        | Zen 4 / Zen 4c | None             | Heterogenous core configuration, may result in serious issues. Incompatible iGPU and NPU. |
| Ryzen 7045 series   | Dragon Range      | Zen 4          | None             | Incompatible iGPU                                                                         |
| Ryzen 7040 series   | Phoenix           | Zen 4 / Zen 4c | None             | Heterogenous core configuration, may result in serious issues. Incompatible iGPU and NPU. |
| Ryzen 7035 series   | Rembrandt-R       | Zen 3+         | None             | Incompatible iGPU                                                                         |
| Ryzen 7030 series   | Barceló-R         | Zen 3          | Catalina (10.15) |                                                                                           |
| Ryzen 7020 series   | Mendocino         | Zen 2          | None             | Incompatible iGPU                                                                         |
| Ryzen 6000 series   | Rembrandt         | Zen 3+         | None             | Incompatible iGPU                                                                         |
| Ryzen 5000 series   | Lucienne          | Zen 2          | Catalina (10.15) |                                                                                           |
| Ryzen 5000 series   | Cezanne / Barceló | Zen 3          | Catalina (10.15) |                                                                                           |
| Ryzen 4000 series   | Renoir            | Zen 2          | Catalina (10.15) |                                                                                           |
| Ryzen 3000 series   | Picasso           | Zen+           | Catalina (10.15) |                                                                                           |
| Ryzen 3000 series   | Dalí              | Zen            | Catalina (10.15) |                                                                                           |
| Ryzen 2000 series   | Raven Ridge       | Zen            | Catalina (10.15) |                                                                                           |

# Workstation CPUs

| Generation               | Product Name | Architecture | Initial Support     | Notes |
| ------------------------ | ------------ | ------------ | ------------------- | ----- |
| Threadripper 7000 series | Storm Peak   | Zen 4        | High Sierra (10.13) |       |
| Threadripper 5000 series | Chagall      | Zen 3        | High Sierra (10.13) |       |
| Threadripper 3000 series | Castle Peak  | Zen 2        | High Sierra (10.13) |       |
| Threadripper 2000 series | Colfax       | Zen+         | High Sierra (10.13) |       |
| Threadripper 1000 series | Whitehaven   | Zen          | High Sierra (10.13) |       |

# Incompatible Chips

| Chip            | Product Name | Architecture   | Notes                                                                             |
| --------------- | ------------ | -------------- | --------------------------------------------------------------------------------- |
| AMD 4800S       | Renoir       | Zen 2          | XBox/Playstation Desktop Kits, behave way differently than desktop chips.         |
| AMD 4700S       | Renoir       | Zen 2          | XBox/Playstation Desktop Kits, behave way differently than desktop chips.         |
| Ryzen Z1 series |              | Zen 4 / Zen 4c | Incompatible iGPU, heterogenous core configuration, may result in serious issues. |

<br>
<h2 align="center">
  <br>
  <div class="navigation-container">
    <a class="nav-button" href="../../../01-CPU/index">&larr; Back Page</a>
    <a class="nav-button" href="../../../02-GPU/index">Next Page &rarr;</a>
  </div>
  <br>
</h2>
