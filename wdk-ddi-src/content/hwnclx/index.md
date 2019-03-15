---
UID: NA:hwnclx
ms.assetid: b41140bd-3a1f-3742-9971-e78555cd7456
ms.date: 05/09/18
ms.keywords: 
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: portal
product:
- Windows
tech.root: gpiobtn
---

# Hwnclx.h header


## -description

This header defines programming interfaces required to provide  hardware-agnostic support of notification components such as LEDs and vibration mechanisms. This support is delivered through the introduction of a Kernel-Mode Driver Framework (KMDF) class extension specifically for hardware notification components that allows for the rapid development of client drivers. A KMDF class extension is essentially a KMDF driver that provides a defined set of functionality for a given class of devices, similar to a port driver in the Windows Driver Model (WDM). This section provides an overview of the architecture of the hardware notification class extension. For additional information about the KMDF, see

For more information, see:

- [Hardware notifications design guide](https://docs.microsoft.com/windows-hardware/drivers/gpiobtn)
