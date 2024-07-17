---
layout: default
title: The Recovery Server Could Not Be Contacted
parent: Troubleshooting Issues
nav_order: 1
has_children: false
has_toc: false
---

<p align="center">
  <img width="650" height="200" src="../../../../assets/Header-HSHTTPFix.png">
</p>
<br>

This quick write-up is meant to teach you how to fix the ``Recovery Server Could Not Be Contacted`` error on versions like High Sierra and older. The error is due to expired SSL Certificates, and as such, we can fix this by downloading the data over HTTP.

To do so, you can utilizie the ``nvram`` command in a Terminal to set the ``IASUCatalogURL`` to be using HTTP over HTTPS.

```bash
nvram IASUCatalogURL="http://swscan.apple.com/content/catalogs/others/index-10.13-10.12-10.11-10.10-10.9-mountainlion-lion-snowleopard-leopard.merged-1.sucatalog"
```

You don't need to restart at all, you can simply try to contact the server again.

Once you finish with this, be sure to reset your NVRAM or set it back to use HTTPS!

The easiest option is simply deleting the variable.

```bash
sudo nvram -d IASUCatalogURL
```

<h4>Thanks for reading!</h4>
