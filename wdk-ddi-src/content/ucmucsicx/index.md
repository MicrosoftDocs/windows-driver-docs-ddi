---
UID: NA:ucmucsicx
ms.assetid: 6839a2d9-d025-3af4-9d57-2d591f143ae1
ms.date: 10/19/2018
ms.keywords:
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: portal
product:
-	Windows
tech.root: usbref
ms.custom: RS5
---

# Ucmucsicx.h header


## -description

This header is the main include header for client drivers of the UcmUcsiCx class extension. The extension provides a transport-agnostic implementation of the [UCSI specification](https://go.microsoft.com/fwlink/p/?LinkId=760658).

Ucmucsicx includes these headers:

[UcmUcsiGlobals.h](..\ucmucsiglobals\index.md)

[UcmUcsiFuncEnum.h](..\ucmucsifuncenum\index.md)

[UcmUcsiDevice.h](..\ucmucsidevice\index.md)

[UcmUcsiSpec.h](..\ucmucsispec\index.md)

[UcmUcsiPpm.h](..\ucmucsispec\index.md)

[UcmUcsiPpmRequests.h](..\ucmucsispec\index.md)

> Do not include the preceding headers directly. Instead, only include Ucmucsicx.h.

For more information, see:
- [Write a UcmUcsi client driver](https://docs.microsoft.com/windows-hardware/drivers/usbcon/write-a-ucsi-driver)
- [Universal Serial Bus (USB)](https://docs.microsoft.com/windows-hardware/drivers/usbcon/write-a-ucsi-driver)
