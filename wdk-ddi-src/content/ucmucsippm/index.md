---
UID: NA:ucmucsippm
author: windows-driver-content
ms.assetid: 6839a2d9-d025-3af4-9d57-2d591f143ae1
ms.author: windowsdriverdev
ms.date: 09/30/2018 
ms.keywords: 
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: portal
tech.root: usbref
---

# Ucmucsippm.h header


## -description

This header provides UCM-UCSI Platform Policy Manager (PPM) declarations. PPM abstracts the details of sending UCSI commands from Operating System Policy Manager (OPM) to PPM and receiving notifications from the PPM. It converts PPM commands to WDFREQUEST objects and forwards them to the client driver.

> Do not include this header. Instead, include Ucmucsicx.h.

For more information, see:
- [Write a UcmUcsi client driver]()
- [Universal Serial Bus (USB)](../_usbref/index.md)