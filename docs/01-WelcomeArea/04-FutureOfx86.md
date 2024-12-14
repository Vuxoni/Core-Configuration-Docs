---
layout: default
title: Future of x86
description: 
parent: Welcome to the Botánica
nav_order: 4
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
  <img width="650" height="200" src="../../assets/Headers/Header-FutureOfx86.png">
</p>

<h2 align="center">What happens if macOS 16 does not support Intel?</h2>
<br>
<p align="center">Then macOS Sequoia (15.X.X) will be the final version that an Intel-based Mac can run. If you've ever purchased or owned an older Mac computer, you'll already know exactly what to expect when updates are no longer compiled for Intel: Your machine will no longer update a full release, but instead gets security updates for up to 3 years (i.e macOS 15.7.8 or similar). After a few more years, more and more applications will require the use of macOS 16 and you'll no longer be able to run the latest versions of your favorite applications, as they will require you to use the latest version of their client or whatever it may be. After a few more years, it is possible that there may be known public CVE's for malware on Intel-based Macs, and by that point, the majority of Hacs will convert to an M-Series Mac, or simply return to Windows or Linux, where it will no longer be viable to run macOS Sequoia (15).</p>

<h2 align="center">I don't own any supported hardware, but can I purchase some?</h2>
<br>
<p align="center">In the twilight years of the Mac operating system supporting x86_64, it no longer makes sense to purchase and build hardware for the sole purpose of running the Mac operating system. While there are exceptions similar to simply purchasing a single crucial part that is missing support such as a Graphics Card or a Wi-Fi card, it no longer makes sense to <b>build</b> a machine from scratch as you will be limited to purchasing hardware that is fairly old by now.</p>

<p align="center">Such an example would be a User who is interested in a laptop to convert in to a Hac, this User will be limited to purchasing 10th Gen Intel Laptops due to the requirement of a supported Graphics Processing Unit, and with the lack of AMD Mobile GPU's in use, in tandem with the last iGPU to be supported on macOS to be 10th Gen, you will be forced to consider an older Intel laptop which may not be worth it by the time macOS dies on x86_64. This does not even account for the rest of the hardware that may or may not be supported on said laptop.</p>

<p align="center">Another example would be a User who needs to purchase supported Graphics hardware for acceleration... As AMD at the time of writing this has announced the newest 8XXX Series of GPUs, and the 7XXX series has been out for some time now, you'd be shocked to hear that the last supported AMD GPU is actually the 6600/XT which released in 2021. This is because macOS only has support for Navi 10, 21, and 23. Theoretically, the most powerful GPU you can purchase is now the 6950 XT (Navi 21). Would it make sense for you to purchase a top of the line GPU for a hobby project if you already own RTX? In this scenario, it makes more sense to purchase an older RX 5XX (Polaris 20) or 4XX (Polaris 10) card, as these are supported as well, and can be found cheaply nowadays if your workload doesn't require much power. 

<h2 align="center">Enough yap! Show me the juicy details!</h2>
<br>
<p align="center">It's time we move on from prerequisites and begin determining hardware compatibilty.</p>

<h2 align="center">
  <br>
  <div class="navigation-container">
    <a class="nav-button" href="03-SettingExpectations.html">&larr; Back Page</a>
    <a class="nav-button" href="../../../hardware/01-Importance">Next Page &rarr;</a>
  </div>
  <br>
</h2>
