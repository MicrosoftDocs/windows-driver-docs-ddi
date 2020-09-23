---
UID: NA:ucmucsippm
title: Ucmucsippm.h header
ms.assetid: 6839a2d9-d025-3af4-9d57-2d591f143ae1
ms.date: 09/30/2018
keywords: ["Ucmucsippm.h header"]
ms.keywords: 
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: portal
tech.root: usbref
ms.custom: RS5
f1_keywords:
 - ucmucsippm
 - ucmucsippm/ucmucsippm
---

# Ucmucsippm.h header


## -description

This header provides declarations for UCM-UCSI Platform Policy Manager (PPM) abstraction within the class extension. This PPM object implements the details of sending UCSI commands from Operating System Policy Manager (OPM) object to the client driver and receiving notifications from the client driver. For sending commands to the client driver, it converts UCSI PPM commands to IOCTLs and forwards them to the client driver which later transports the commands to the actual firmware.

> Do not include this header. Instead, include Ucmucsicx.h.

For more information, see:
- [Write a UcmUcsi client driver](/windows-hardware/drivers/usbcon/write-a-ucsi-driver)
- [Universal Serial Bus (USB)](/windows-hardware/drivers/usbcon)