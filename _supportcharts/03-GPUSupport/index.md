---
layout: default
title: GPU Support Chart
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

  .intel-next-button-container,
  .nvidia-next-button-container {
    text-align: right;
  }

  .intel-next-button,
  .nvidia-next-button {
    margin: 10px;
  }
</style>

<p align="center">
  <img width="650" height="200" src="../../../assets/Header-GPUSupportChart.png">
</p>

<h4 align="center">This page is a stub temporarily, but this page should:</h4>
<br>

1. Help the user find their GPU by Vendor.
2. Go over general notes that affect all GPUs and iGPUs.

{: .note }
Reasoning for the order of options in the nav bar is due to people's typical first option available. For the most part, most users start with iGPU support, and then begin considering their dedicated graphics. As such, we then display AMD as the next "best" option, and followed finally by NVIDIA. The order is from top to bottom, not inversed. As such, do not assume NVIDIA is the best choice.

<h2 align="center">
  <br>
  <div class="intel-next-button-container">
    <a class="intel-next-button" href="../01-Intel">Intel &rarr;</a>
  </div>
  <div class="nvidia-next-button-container">
    <a class="nvidia-next-button" href="../02-AMD">AMD &rarr;</a>
  </div>
  <div class="navigation-container">
    <a class="nav-button" href="../../02-CPUSupport/index">&larr; Back Page</a>
    <a class="nav-button" href="../03-NVIDIA">NVIDIA &rarr;</a>
  </div>
  <br>
</h2>
