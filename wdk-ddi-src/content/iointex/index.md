---
UID: NA:iointex
ms.assetid: dc0c0187-51c0-3402-8643-c7e2175b1b69
ms.author: windowsdriverdev
ms.date: 02/27/18
ms.keywords: 
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: portal
---

# Iointex.h header



This header is used by Windows kernel. For more information, see
- [Windows kernel](../_kernel/index.md)

Iointex.h contain these programming interfaces:


## Functions

| Title   | Description   |
| ---- |:---- |
| [WdmlibIoConnectInterruptEx function](nf-iointex-wdmlibioconnectinterruptex.md) | The WdmlibIoConnectInterruptEx function registers an interrupt-handling routine for a device's interrupts. |
| [WdmlibIoDisconnectInterruptEx function](nf-iointex-wdmlibiodisconnectinterruptex.md) | The WdmlibIoDisconnectInterruptEx function unregisters an interrupt service routine (ISR) that was registered by a previous call to the WdmlibIoConnectInterruptEx function. |
| [WdmlibIoGetAffinityInterrupt function](nf-iointex-wdmlibiogetaffinityinterrupt.md) | The WdmlibIoGetAffinityInterrupt function gets the group affinity of an interrupt object. |
