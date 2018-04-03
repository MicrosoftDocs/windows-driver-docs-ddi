---
UID: NA:sercx
ms.assetid: 742ea1bd-45ef-3fce-abc3-5de9640cf02d
ms.author: windowsdriverdev
ms.date: 04/03/18
ms.keywords: 
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: portal
---

# Sercx.h header


## -description


This header is used by serports. For more information, see:

- [Serial port](../_serports/index.md)

This section contains reference information about the device driver interface (DDI) of the serial framework extension. Starting with Windows 8.1, version 2 of the serial framework extension (SerCx2) is a system-supplied component. SerCx2 replaces version 1 of the serial framework extension (SerCx), which was introduced in Windows 8.

SerCx2 simplifies the design of a serial controller driver by performing many of the functions that are generic to all serial controller drivers. The serial controller driver can be relatively small and performs only hardware-specific processing tasks. SerCx2 works with the serial controller driver to handle I/O requests that clients (drivers for serially connected peripheral devices) send to the serial controller.

A serial controller is a universal asynchronous receiver/transmitter (UART) or similar device that has a serial communications interface. For more information, see Serial Controller Drivers Overview.


In this section


Topic
Description




Version 2 Serial Framework Extension (SerCx2) Reference



This section contains reference information about the device driver interface (DDI) of version 2 of the serial framework extension (SerCx2). Starting with Windows 8.1, a serial controller driver uses this DDI to communicate with SerCx2. 





Version 1 Serial Framework Extension (SerCx) Reference



This section contains reference information about the device driver interface (DDI) of version 1 of the serial framework extension (SerCx). SerCx was introduced in Windows 8, but was replaced by version 2 of the serial framework interface (SerCx2) starting with Windows 8.1.



 


Send comments about this topic to Microsoft

