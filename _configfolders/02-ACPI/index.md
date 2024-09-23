---
layout: default
title: ACPI
nav_order: 2
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

  .ssdttime-next-button-container {
    text-align: right;
  }

  .ssdttime-next-button {
    margin: 10px;
    top: 0px;
    bottom: 0px;
    left: 0px;
    right: 0px;
  }
</style>

<p align="center">
  <img width="650" height="200" src="../../../assets/Header-OpenCore-ACPI.png">
</p>

## First of all, whats ACPI?
ACPI stands for Advanced Configuration and Power Interface. It is an industry standard for power management that most major manufacturers use. It offers the possibility of hardware detection, device configuration and energy management. It has been the successor to <a href="https://en.wikipedia.org/wiki/Advanced_Power_Management">APM</a> since the late 1990s.

ACPI offers, among other things, different operating modes (C-, S- and other states), which you can sometimes read about in the BIOS. 
The firmware of each device provides several ACPI tables. These contain the "electrical blueprints" of the system. Most of the information is contained in the DSDT (Differentiated System Description Table). Oversimplified, the other SSDTs (Secondary System Description Tables) supplement the DSDT.
These tables are compiled in AML (ACPI Machine Language). They are therefore not readable by us as humans. However, with the help of a compiler and disassembler we can translate between the machine language and ASL (ACPI Source Language) that we can read.

If you want to learn more about compiling and disassembling ACPI, you can find <a href="https://www.intel.com/content/www/us/en/download/774881/acpi-component-architecture-downloads-windows-binary-tools.html">iASL</a> or <a href="https://github.com/acidanthera/MaciASL">MaciASL</a> here.

## Why do we care about ACPI?
As we know, there are many more PC and laptop configurations than Mac configurations. In other words, this means: macOS is much more adapted to specific systems. Why should they cover all possible configurations? So we have to approach these configurations. This also includes adapting at the ACPI level.
Unfortunately, macOS is very picky when it comes to the entries in the tables. We want to make a bunch of changes in the form of creating SSDTs, because otherwise we won't be able to use macOS.

These changes can be made with an injection of an edited DSDT, as it was done under Clover. Another method is adding individual patches in our config.plist under ACPI -> Patch.

## ​What SSDTs do I need?
First of all, this guide covers two ways to get the SSDTs needed. You have the option to generate them yourself or do everything manually.
Please note, however, that there are SSDTs that cannot be generated (e.g. SSDT-CPUR). In almost every case, it's recommended to generate the SSDTs. However, if you want to delve deeper into the subject or feel like it, you can also choose the manual approach.


<h2 align="center">Placeholder Information</h2>

<h4 align="center">This page is a stub, we have enabled the ToC for the moment, but this page should:</h4>
<br>

1. Explain ACPI and SSDTs
2. Show a Chart of required SSDTs per CPU
3. Show a Chart of additional SSDTs and their purpose
4. Explain the methods of creating such SSDTs
5. Show two buttons taking users to either SSDTTime or Manual method

<h2 align="center">To begin, select the tool of choice:</h2>
<br>

<h2 align="center">
  <br>
  <div class="ssdttime-next-button-container">
  <a class="ssdttime-next-button" href="../01-SSDTTime/index/">SSDTTime &rarr;</a>
  </div>
  <div class="navigation-container">
    <a class="nav-button" href="../../01-Introduction/index/">&larr; Back Page</a>
    <a class="nav-button" href="../02-Manual/index/">Manual Method &rarr;</a>
  </div>
  <br>
</h2>
