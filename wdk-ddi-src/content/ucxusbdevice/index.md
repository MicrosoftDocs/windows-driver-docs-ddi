---
UID: NA:ucxusbdevice
title: Ucxusbdevice.h header
ms.assetid: 2cf71389-08f1-3c73-b478-7efa6045e05e
ms.date: 05/09/2018
keywords: ["Ucxusbdevice.h header"]
ms.keywords: USB host controller driver
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: portal
product:
- Windows
tech.root: usbref
---

# Ucxusbdevice.h header


## -description


This header is used to write a USB host controller driver. The USB host controller extension is a system-supplied driver (Ucx01000.sys). This driver is implemented as a framework class extension by using the Windows Driver Framework programming interfaces. The host controller driver serves as the client driver to that class extension. While a host controller driver handles hardware operations and events, power management, and PnP events, UCX serves as an abstracted interface that queues requests to the host controller driver, and performs other tasks.

> Do not include this header directly. Instead include Ucxclass.h

For more information, see:

- [Developing Windows drivers for USB host controllers](https://docs.microsoft.com/windows-hardware/drivers/usbcon/developing-windows-drivers-for-usb-host-controllers)
- [Universal Serial Bus (USB)](../_usbref/index.md)
