---
UID: NA:ucmucsippm
author: windows-driver-content
ms.assetid: 6839a2d9-d025-3af4-9d57-2d591f143ae1
ms.author: windowsdriverdev
ms.date: 09/30/201809/30/2018 
ms.keywords: 
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: portal
tech.root: usbref
---

# Ucmucsippm.h header


## -description

UCM-UCSI Platform Policy Manager (PPM) abstracts the details of sending UCSI commands from Operating System Policy Manager (OPM) to PPM and receiving notifications from the PPM. It converts PPM commands to WDFREQUEST objects and forwards them to the client driver. UCSI commands are sent to the client driver as I/O control codes, declared in this header.

For information about UCSI commands, see [UCSI spec version 1.1](https://www.intel.com/content/dam/www/public/us/en/documents/technical-specifications/usb-type-c-ucsi-spec.pdf).

> Do not include this header. Instead, include Ucmucsicx.h.

For more information, see:
- [Write a UcmUcsi client driver]()
- [Universal Serial Bus (USB)](../_usbref/index.md)