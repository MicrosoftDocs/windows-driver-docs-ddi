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

This header is the main include header for client drivers of the UcmUcsiCx class extension. The extension provides a transport-agnostic implementation of the [UCSI specification](http://go.microsoft.com/fwlink/p/?LinkId=760658).

Ucmucsicx includes these headers:

[UcmUcsiGlobals.h](..\ucmucsiglobals\index.md)

[UcmUcsiFuncEnum.h](..\ucmucsifuncenum\index.md)

[UcmUcsiDevice.h](..\ucmucsidevice\index.md)

[UcmUcsiSpec.h](..\ucmucsispec\index.md)

[UcmUcsiPpm.h](..\ucmucsispec\index.md)

[UcmUcsiPpmRequests.h](..\ucmucsispec\index.md)

> Do not include the preceding headers directly. Instead, only include Ucmucsicx.h.

For more information, see:
- [Write a UcmUcsi client driver](https://docs.microsoft.com/en-us/windows-hardware/drivers/usbcon/write-a-ucsi-driver)
- [Universal Serial Bus (USB)](https://docs.microsoft.com/en-us/windows-hardware/drivers/usbcon/write-a-ucsi-driver)
