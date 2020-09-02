---
UID: TP:gpiobtn
title: Hardware notifications
ms.assetid: 44f18b04-69c6-3937-b9a0-04797d713edc
ms.date: 05/09/2018
keywords: ["Hardware notifications"]
ms.keywords: 
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: portal
---

# Hardware notifications

## -description

Windows provides an infrastructure for the hardware-agnostic support of notification components such as LEDs and vibration mechanisms. This support is delivered through the introduction of a Kernel-Mode Driver Framework (KMDF) class extension specifically for hardware notification components that allows for the rapid development of client drivers. A KMDF class extension is essentially a KMDF driver that provides a defined set of functionality for a given class of devices, similar to a port driver in the Windows Driver Model (WDM). This section provides an overview of the architecture of the hardware notification class extension. 

For additional information about the KMDF, see [Using WDF to Develop a Driver](https://docs.microsoft.com/windows-hardware/drivers/wdf/using-the-framework-to-develop-a-driver).

To provide support for hardware notifications, you need:

- [hwnclx.h](https://docs.microsoft.com/windows-hardware/drivers/ddi/hwnclx/)
