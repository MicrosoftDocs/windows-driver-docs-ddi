---
UID: NA:wiamicro
ms.assetid: 6e3ffcb6-f08e-3947-9774-2adf8c435369
ms.author: windowsdriverdev
ms.date: 02/27/18
ms.keywords: 
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: portal
---

# Wiamicro.h header



This header is used by Imaging devices. For more information, see
- [Imaging devices](../_image/index.md)

Wiamicro.h contain these programming interfaces:


## Functions

| Title   | Description   |
| ---- |:---- |
| [MicroEntry function](nf-wiamicro-microentry.md) | The MicroEntry function responds to commands sent by the WIA Flatbed driver. |
| [Scan function](nf-wiamicro-scan.md) | The Scan function reads data from the device and returns the data to the WIA Flatbed driver. |
| [SetPixelWindow function](nf-wiamicro-setpixelwindow.md) | The SetPixelWindow function sets the image area to be scanned. |

## Structures

| Title   | Description   |
| ---- |:---- |
| [VAL structure](ns-wiamicro-val.md) | The VAL structure is used by the microdriver and WIA Flatbed driver to pass information between each other. |
| [_RANGEVALUE structure](ns-wiamicro-_rangevalue.md) | The RANGEVALUE structure is used by a microdriver to communicate to the WIA Flatbed driver the legal values for a microdriver function parameter. |
| [_SCANINFO structure](ns-wiamicro-_scaninfo.md) | The SCANINFO structure is used to store and communicate information about a scan acquisition. |
| [_SCANWINDOW structure](ns-wiamicro-_scanwindow.md) | The SCANWINDOW structure is used by the WIA Flatbed driver to tell the microdriver what image area to scan. |
