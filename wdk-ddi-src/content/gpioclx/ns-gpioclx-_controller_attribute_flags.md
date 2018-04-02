---
UID: NS:gpioclx._CONTROLLER_ATTRIBUTE_FLAGS
title: "_CONTROLLER_ATTRIBUTE_FLAGS"
author: windows-driver-content
description: The CONTROLLER_ATTRIBUTE_FLAGS structure describes the hardware attributes of the general-purpose I/O (GPIO) controller device.
old-location: gpio\controller_attribute_flags.htm
old-project: GPIO
ms.assetid: 4D3DE8AE-99FB-48C8-A2FC-099CA908EC18
ms.author: windowsdriverdev
ms.date: 2/15/2018
ms.keywords: "*PCONTROLLER_ATTRIBUTE_FLAGS, CONTROLLER_ATTRIBUTE_FLAGS, CONTROLLER_ATTRIBUTE_FLAGS structure [Parallel Ports], GPIO.controller_attribute_flags, PCONTROLLER_ATTRIBUTE_FLAGS, PCONTROLLER_ATTRIBUTE_FLAGS structure pointer [Parallel Ports], _CONTROLLER_ATTRIBUTE_FLAGS, gpioclx/CONTROLLER_ATTRIBUTE_FLAGS, gpioclx/PCONTROLLER_ATTRIBUTE_FLAGS"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: gpioclx.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: Supported starting with Windows 8.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: PASSIVE_LEVEL
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	Gpioclx.h
api_name:
-	CONTROLLER_ATTRIBUTE_FLAGS
product:
- Windows
targetos: Windows
req.typenames: CONTROLLER_ATTRIBUTE_FLAGS, *PCONTROLLER_ATTRIBUTE_FLAGS
---

# _CONTROLLER_ATTRIBUTE_FLAGS structure


## -description


The <b>CONTROLLER_ATTRIBUTE_FLAGS</b> structure describes the hardware attributes of the general-purpose I/O (GPIO) controller device.


## -struct-fields




### -field AsULONG

 




#### - ActiveInterruptsAutoClearOnRead

Whether active interrupts are automatically cleared when the GPIO controller driver reads them. If this flag is set, GpioClx assumes that interrupts are automatically cleared when they are read and, therefore, does not explicitly request that the driver clear active interrupts during interrupt processing. Otherwise, GpioClx explicitly requests that active interrupts be cleared. For more information, see the discussion of the <b>ActiveInterruptsAutoClearOnRead</b> flag bit in <a href="https://msdn.microsoft.com/library/windows/hardware/hh439479">GPIO_CLIENT_REGISTRATION_PACKET</a>.


#### - BankIdlePowerMgmtSupported

Whether the GPIO controller supports component-level power management. If this flag is set, one or more banks in the GPIO controller can be put into a low-power state independently of the other banks in the GPIO controller. Otherwise, the power states of the banks cannot be individually controlled. This flag can be set only for a GPIO controller whose registers are memory-mapped, as indicated by the <b>MemoryMappedController</b> flag. Typically, only a GPIO controller that is an integrated part of a SoC module is memory-mapped. A GPIO controller that is external the SoC module is typically not memory-mapped.


#### - DeviceIdlePowerMgmtSupported

Whether the GPIO controller supports device-level power management. If this flag is set, the GPIO controller can be put into a low-power (D3) state when it is idle (that is, when there are no active connections to the controller). Otherwise, the GPIO controller remains in the fully on (D0) power state any time the controller is turned on.


#### - EmulateActiveBoth

Whether the GPIO controller driver requires GpioClx to emulate active-both interrupts in software. If this flag is set, GpioClx emulates active-both interrupts in software. Otherwise, GpioClx does not emulate active-both interrupts. For more information, see Remarks.


#### - EmulateDebouncing

Whether debouncing of input signals to GPIO pins is performed by software or by hardware. If this flag is set, the GPIO controller requires debouncing to be emulated in software by the GPIO framework extension (GpioClx). Otherwise, debouncing is performed by hardware, and software-emulated debouncing is unnecessary.


#### - FormatIoRequestsAsMasks

Whether callback functions that read from or write to GPIO pins should specify read and write values as 64-bit masks. If this flag is set, GpioClx uses <a href="https://msdn.microsoft.com/library/windows/hardware/hh439406">CLIENT_ReadGpioPinsUsingMask</a> callbacks that read GPIO pin values into masks, and <a href="https://msdn.microsoft.com/library/windows/hardware/hh439445">CLIENT_WriteGpioPinsUsingMask</a> callbacks that use masks to designate GPIO pins to set and clear. Otherwise, GpioClx uses <a href="https://msdn.microsoft.com/library/windows/hardware/hh439404">CLIENT_ReadGpioPins</a> and <a href="https://msdn.microsoft.com/library/windows/hardware/hh439439">CLIENT_WriteGpioPins</a> callbacks that use arrays of pin numbers to specify which GPIO pins to access. For more information, see the discussion of the <b>FormatIoRequestsAsMasks</b> flag bit in <a href="https://msdn.microsoft.com/library/windows/hardware/hh439479">GPIO_CLIENT_REGISTRATION_PACKET</a>.


#### - MemoryMappedController

Whether the GPIO controller is memory-mapped. If this flag is set, the hardware registers of the GPIO controller are mapped to memory addresses, and can be directly accessed by a GPIO controller driver routine that is running at DIRQL. Otherwise, the registers of the GPIO controller can be accessed only by means of I/O requests, which the GPIO controller driver sends at IRQL = PASSIVE_LEVEL. For more information, see Remarks.


#### - Reserved

Reserved for system use.


## -remarks



The <b>Flags</b> member of the <a href="https://msdn.microsoft.com/library/windows/hardware/hh439358">CLIENT_CONTROLLER_BASIC_INFORMATION</a> structure is a <b>CONTROLLER_ATTRIBUTE_FLAGS</b> structure.

GpioClx implements an interrupt service routine (ISR) to service interrupts from the GPIO controller. If the <b>MemoryMappedController</b> flag bit is set, this ISR directly accesses the hardware registers of the GPIO controller. Otherwise, the ISR schedules a worker thread to handle the interrupt, and this worker thread, which runs at IRQL = PASSIVE_LEVEL, calls the driver's interrupt-related callback functions to handle the interrupt. These functions use I/O requests to transfer data and control information to and from the GPIO controller's registers. Because these I/O requests are sent from a passive-level thread, they can be sent synchronously.

For more information about the <b>MemoryMappedController</b> flag bit, see <a href="https://msdn.microsoft.com/638B52A0-CB8D-4A79-B7D1-ED2474E46DAE">Interrupt-Related Callbacks</a>.

An active-both interrupt is an edge-triggered interrupt for which an interrupt request is indicated by a low-to-high or a high-to-low transition on the interrupt line. After a low-to-high transition signals an interrupt request, the interrupt line remains high until a high-to-low transition signals the next interrupt request. Similarly, after a high-to-low transition signals an interrupt request, the interrupt line remains low until a low-to-high transition signals the next interrupt request.

A push-button device is typically connected to an active-both interrupt. An interrupt is generated when the user presses the button, and another interrupt is generated when the button is released. If a device driver's ISR is connected to an active-both interrupt, the ISR is called on both rising and falling edges of the signal line.

Some GPIO controllers implement active-both interrupt inputs in hardware. However, if the hardware does not support active-both interrupts, the GPIO controller driver sets the <b>EmulateActiveBoth</b> flag to request that GpioClx emulate active-both interrupts in software. A driver that sets this flag must implement a <a href="https://msdn.microsoft.com/library/windows/hardware/hh698243">CLIENT_ReconfigureInterrupt</a> callback function. To emulate an active-both interrupt pin, GpioClx calls this function to alternately configure a GPIO pin for active-high and active-low level-mode interrupts.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/hh439358">CLIENT_CONTROLLER_BASIC_INFORMATION</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh439395">CLIENT_QueryActiveInterrupts</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh439404">CLIENT_ReadGpioPins</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh439406">CLIENT_ReadGpioPinsUsingMask</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh698243">CLIENT_ReconfigureInterrupt</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh439439">CLIENT_WriteGpioPins</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh439445">CLIENT_WriteGpioPinsUsingMask</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh439479">GPIO_CLIENT_REGISTRATION_PACKET</a>
 

 

