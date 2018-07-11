---
UID: TP:battery
author: windows-driver-content
ms.assetid: 7433fa8b-bcff-3cc7-a61e-27c29a2f632b
ms.author: windowsdriverdev
ms.date: 07/10/18
ms.keywords: 
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: portal
---

# Battery

## -description

A battery typically has a pair of drivers: the generic battery class driver that Microsoft provides, and a miniclass driver written specifically for that individual type of battery.

The class driver defines the overall functionality of the batteries in the system and interacts with the power manager.

To develop Battery, you need these headers:

 * [charging.h](..\charging\index.md)
 * [hpmi.h](..\hpmi\index.md)
 * [upssvc.h](..\upssvc\index.md)

For the programming guide, see [Battery Devices Design Guide](https://docs.microsoft.com/windows-hardware/drivers/battery).

