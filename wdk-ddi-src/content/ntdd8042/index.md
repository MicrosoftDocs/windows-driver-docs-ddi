---
UID: NA:ntdd8042
ms.assetid: 20253ca3-2ef9-33f0-991d-bd37be11cc04
ms.author: windowsdriverdev
ms.date: 02/27/18
ms.keywords: 
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: portal
---

# Ntdd8042.h header



This header is used by Human Interface Devices (HID). For more information, see
- [Human Interface Devices (HID)](../_hid/index.md)

This section includes the following topics about I8042prt, the system function driver for PS/2-style keyboard and mouse devices

Note that the operational constraints of I8042prt do not apply to Sermouse, the Windows system function driver for a serial mouse.

- Callbacks that an upper-level keyboard filter driver can provide to supplement the operation of I8042prt:

    PI8042_KEYBOARD_INITIALIZATION_ROUTINE
    PI8042_KEYBOARD_ISR


- Callbacks that an upper-level mouse filter driver can provide to supplement the operation of I8042prt:

    PI8042_MOUSE_ISR


- Callbacks that I8042prt provides that an upper-level filter drivers can use:

    PI8042_ISR_WRITE_PORT
    PI8042_QUEUE_PACKET
    PI8042_SYNCH_READ_PORT
    PI8042_SYNCH_WRITE_PORT



I8042prt uses IOCTL_INTERNAL_I8042_HOOK_KEYBOARD and IOCTL_INTERNAL_I8042_HOOK_KEYBOARD requests to add, or hook, the filter driver callbacks into the operation of I8042prt. A hook request also passes pointers to the I8042prt keyboard callbacks to the filter driver.



