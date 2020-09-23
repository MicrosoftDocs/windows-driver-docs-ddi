---
UID: NA:udecxwdfdevice
title: Udecxwdfdevice.h header
ms.assetid: d0a5a6e1-0a40-3c57-8704-6ba20faac4d9
ms.date: 05/09/2018
keywords: ["Udecxwdfdevice.h header"]
ms.keywords: 
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: portal
tech.root: usbref
f1_keywords:
 - udecxwdfdevice
 - udecxwdfdevice/udecxwdfdevice
---

# Udecxwdfdevice.h header


## -description

This header is used for developing an emulated Universal Serial Bus (USB) host controller driver and a connected virtual USB device. Both components are combined into a single KMDF driver that communicates with the Microsoft-provided USB device emulation class extension (UdeCx).

> Do not include this header directly. Instead include Udecx.h.

For more information, see:

- [Universal Serial Bus (USB)](../_usbref/index.md)
- [Developing Windows drivers for emulated USB devices (UDE)](/windows-hardware/drivers/usbcon/developing-windows-drivers-for-emulated-usb-host-controllers-and-devices)