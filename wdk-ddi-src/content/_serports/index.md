---
UID: TP:serports
ms.assetid: a99541fb-a2d1-3e81-9efd-97d9eecc1ed4
ms.author: windowsdriverdev
ms.date: 04/02/18
ms.keywords: 
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: portal
---

# Serports

## -description

Overview of the Serports technology.

To develop Serports, you need these headers:

 * [sercx.h](..\sercx\index.md)
 * [sercxfuncenum.h](..\sercxfuncenum\index.md)
 * [serfuncenum.h](..\serfuncenum\index.md)
 * [uart.h](..\uart\index.md)



This reference section describes the Windows serial I/O request interface that is used by drivers and applications to send I/O requests to serial ports. Also described is the device driver interface (DDI) that an extension-based serial controller driver uses to communicate with version 1 or 2 of the serial framework extension (SerCx or SerCx2). The serial I/O request interface is supported by SerCx and SerCx2, and by the inbox serial driver, Serial.sys. Serial.sys is augmented by the Serenum service and the COM port database.

For more information, see Serial Controller Drivers Overview.


In this section


Extension-Based Serial Controller Driver Reference


Serial I/O Request Reference


Serial Controller Driver reference in SDK header files




Send comments about this topic to Microsoft

