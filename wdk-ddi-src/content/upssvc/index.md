---
UID: NA:upssvc
ms.assetid: 56f0ed8e-9ec7-30ec-98d5-fabcd442174f
ms.author: windowsdriverdev
ms.date: 02/26/18
ms.keywords: 
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: portal
---

# Upssvc.h header



This header is used by Battery. For more information, see
- [Battery](../_battery/index.md)

Upssvc.h contain these programming interfaces:


## Functions

| Title   | Description   |
| ---- |:---- |
| [UPSCancelWait function](nf-upssvc-upscancelwait.md) | The UPSCancelWait function cancels all waits initiated by calls to UPSWaitForStateChange. |
| [UPSGetState function](nf-upssvc-upsgetstate.md) | The UPSGetState function returns the operational state of the UPS. |
| [UPSInit function](nf-upssvc-upsinit.md) | The UPSInit function initializes a UPS minidriver, opens communication to the UPS unit, updates the registry, and causes the minidriver to start monitoring the UPS unit. |
| [UPSStop function](nf-upssvc-upsstop.md) | The UPSStop function causes a UPS minidriver to stop monitoring its UPS unit. |
| [UPSTurnOff function](nf-upssvc-upsturnoff.md) | The UPSTurnOff function turns off the UPS unit's power outlets, after a specified delay time. |
| [UPSWaitForStateChange function](nf-upssvc-upswaitforstatechange.md) | The UPSWaitForStateChange function waits until a specified UPS state changes, or until a time-out interval elapses. |
