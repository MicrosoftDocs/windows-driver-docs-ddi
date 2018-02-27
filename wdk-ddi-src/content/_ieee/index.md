---
UID: TP:ieee
ms.assetid: 59b7bc84-1989-38ca-a623-40657bb0f3b5
ms.author: windowsdriverdev
ms.date: 02/26/18
ms.keywords: 
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: portal
---

# IEEE 1394 bus


Overview of the IEEE 1394 bus technology.

To develop IEEE 1394 bus, you need these headers:

 * [1394.h](..\1394\index.md)
 * [61883.h](..\61883\index.md)

For the programming guide, see [IEEE 1394 bus](https://docs.microsoft.com/en-us/windows-hardware/drivers/ieee).

An IEEE 1394 device driver must communicate with its device by submitting IRPs down the device stack to the 1394 bus driver.

An IEC-61883 client driver must communicate with its device by submitting IRPs down the device stack to the IEC-61883 protocol driver. 

To use these I/O requests, include the header file 61883.h, which is included in the Microsoft Windows Driver Kit (WDK).

Send comments about this topic to Microsoft

