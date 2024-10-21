---
layout: default
title: ACPI
nav_order: 1
parent: Explanations
has_toc: false
---

# ACPI

The ACPI section of OpenCore’s config.plist is essential for managing and customizing the Advanced Configuration and Power Interface (ACPI) tables, which play a crucial role in hardware initialization and power management.

{: .warning }
Don't focus on pictures. They are just placeholders - all the information is written down.

## Add
In the ``Add`` section, you can include custom ACPI tables, such as SSDTs (Secondary System Description Tables). These tables are used to inject or override ACPI methods and devices. For instance, you might add a custom SSDT to enable specific hardware features or to fix compatibility issues. Each entry in this section specifies the path to the ACPI table file and whether it is enabled.

[![ACPI->Add](/assets/config.plist/ACPI->Add.png)](/assets/config.plist/ACPI->Add.png)

| Key     | Type    | Description                                                                                                                                      |
| ------- | ------- | ------------------------------------------------------------------------------------------------------------------------------------------------ |
| Comment | String  |                                                                                                                                                  |
| Enabled | Boolean | Enables loading of the selected table.                                                                                                     |
| Path    | String  | Defines the path of the table to be loadded. Opencore looks for tables with the specified name in OC->ACPI, but you can also specify subfolders. |

This along with many of the other sections will be auto-filled when using CorpNewt's OCSnapshot.

{: .note }
Adding a SSDT will add a new table to your ACPI stack. However, if you add a (modified) DSDT table to ``ACPI->Add``, it will replace your existing DSDT table.

## Delete
The ``Delete`` section allows you to remove specific ACPI tables or entries from the ACPI stack. This can be useful if certain tables are causing conflicts or if you need to replace them with custom versions - the most common usecase is dropping ``DMAR`` tables. You can specify the table signatures and table length or OEM table IDs of the ACPI tables you want to delete. This ensures that only the targeted tables are removed, leaving the rest of the ACPI tables intact.

[![ACPI->Block](/assets/config.plist/ACPI->Block.png)](/assets/config.plist/ACPI->Block.png)

| Key            | Type    | Description                                                                            |
| -------------- | ------- | -------------------------------------------------------------------------------------- |
| All            | Boolean | This quirk enabled will delete all tables matching the OEM Table ID / Table Signature. |
| Comment        | String  |                                                                                        |
| Enabled        | Boolean | Enables the removal of the selected table.                                             |
| OEM Table ID   | Data    | ID of the table to be removed.                                                         |
| TableLength    | Integer | Length of the table to be removed.                                                     |
| TableSignature | Data    | Table signature of the table to be removed.                                            |

## Patch
In the ``Patch`` section, you can apply binary patches to existing ACPI tables. This involves specifying patterns to find and replace within the ACPI tables. For example, you might patch a table to change device names or to modify specific methods. Each patch entry includes a comment for documentation, the find and replace patterns, and whether the patch is enabled.

[![ACPI->Patch](/assets/config.plist/ACPI->Patch.png)](/assets/config.plist/ACPI->Patch.png)

| Key            | Type    | Description |
| -------------- | ------- | ----------- |
| Base           | String  | Base path   |
| BaseSkip       | Integer |             |
| Comment        | String  |             |
| Count          | Integer |             |
| Enabled        | Boolean | Enables     |
| Find           | Data    |             |
| Limit          | Integer |             |
| Mask           | Data    |             |
| OemTableId     | Data    |             |
| Replace        | Data    |             |
| ReplaceMask    | Data    |             |
| Skip           | Integer |             |
| TableLength    | Integer |             |
| TableSignature | Data    |             |

# Info needs to be added.

## Quirks

The Quirks section includes various settings that modify ACPI behavior to improve compatibility and stability. These settings can be relevant on some systems for ensuring that your system boots correctly and operates smoothly.

[![ACPI->Quirks](/assets/config.plist/ACPI->Quirks.png)](/assets/config.plist/ACPI->Quirks.png)

### FadtEnableReset
###### Type: Boolean
Only relevant on legacy hardware ([non-UEFI hardware](https://en.wikipedia.org/wiki/BIOS){:target="_blank"}) when shutting down results in a reboot. The FADT table (Fixed ACPI Description Table) is in some cases too small to contain the required reset code - OpenCore tries to add the code with this quirk enabled.

### NormalizeHeaders
###### Type: Boolean
Used for cleaning up ACPI headers in [High Sierra](https://alextjam.es/debugging-appleacpiplatform/){:target="_blank"}. This is a cleaner workarround compared to [dropping MATS tables](https://www.insanelymac.com/forum/topic/324194-pre-release-macos-high-sierra/page/10/#comment-2437554){:target="_blank"}.  

### RebaseRegions
###### Type: Boolean

### ResetHwSig
###### Type: Boolean

### ResetLogoStatus
###### Type: Boolean

Needed on systems where the BIOS splash screen gets stuck and won't clear. It tries to resolve issues related to [BGRT](https://wiki.osdev.org/BGRT){:target="_blank"} (Boot Graphics Record Table). BGRT is a UEFI table that provides information about the boot logo displayed by the firmware. It includes details like the logo’s position and dimensions. When the ResetLogoStatus quirk is enabled, it can help manage or reset the BGRT settings, ensuring that the boot logo is displayed correctly.

### SyncTableIds
###### Type: Boolean

