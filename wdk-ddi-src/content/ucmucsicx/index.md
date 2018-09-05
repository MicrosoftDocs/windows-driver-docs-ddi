---
UID: NA:ucmucsicx
author: windows-driver-content
ms.assetid: 6839a2d9-d025-3af4-9d57-2d591f143ae1
ms.author: windowsdriverdev
ms.date: 
ms.keywords: 
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: portal
tech.root: usbref
---

# Ucmucsicx.h header


## -description

This header is the main include header for client drivers of the UcmUcsiCx class extension. The extension provides a transport-agnostic implementation of the UCSI specification.

Ucmucsicx includes these headers:

UcmUcsiGlobals.h

UcmUcsiFuncEnum.h

UcmUcsiDevice.h

UcmUcsiSpec.h

UcmUcsiPpm.h

UcmUcsiPpmRequests.h

> Do not include the preceding headers directly. Instead, only include Ucmucsicx.h.

For more information, see:
- [Write a UcmUcsi client driver]()
- [Universal Serial Bus (USB)](https://docs.microsoft.com/en-us/windows-hardware/drivers/usbcon/write-a-ucsi-driver)
