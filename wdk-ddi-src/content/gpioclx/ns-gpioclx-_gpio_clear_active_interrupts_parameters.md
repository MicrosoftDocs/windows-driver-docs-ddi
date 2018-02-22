---
UID: NS:gpioclx._GPIO_CLEAR_ACTIVE_INTERRUPTS_PARAMETERS
title: "_GPIO_CLEAR_ACTIVE_INTERRUPTS_PARAMETERS"
author: windows-driver-content
description: The GPIO_CLEAR_ACTIVE_INTERRUPTS_PARAMETERS structure describes a set of general-purpose I/O (GPIO) interrupt pins to clear.
old-location: gpio\gpio_clear_active_interrupts_parameters.htm
old-project: GPIO
ms.assetid: 71DC78B0-F987-4FFB-B3D0-E7AD88EECDA3
ms.author: windowsdriverdev
ms.date: 2/15/2018
ms.keywords: "*PGPIO_CLEAR_ACTIVE_INTERRUPTS_PARAMETERS, PGPIO_CLEAR_ACTIVE_INTERRUPTS_PARAMETERS, PGPIO_CLEAR_ACTIVE_INTERRUPTS_PARAMETERS structure pointer [Parallel Ports], GPIO.gpio_clear_active_interrupts_parameters, gpioclx/GPIO_CLEAR_ACTIVE_INTERRUPTS_PARAMETERS, gpioclx/PGPIO_CLEAR_ACTIVE_INTERRUPTS_PARAMETERS, GPIO_CLEAR_ACTIVE_INTERRUPTS_PARAMETERS, GPIO_CLEAR_ACTIVE_INTERRUPTS_PARAMETERS structure [Parallel Ports], _GPIO_CLEAR_ACTIVE_INTERRUPTS_PARAMETERS"
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	Gpioclx.h
apiname:
-	GPIO_CLEAR_ACTIVE_INTERRUPTS_PARAMETERS
product: Windows
targetos: Windows
req.typenames: "*PGPIO_CLEAR_ACTIVE_INTERRUPTS_PARAMETERS, GPIO_CLEAR_ACTIVE_INTERRUPTS_PARAMETERS"
---

# _GPIO_CLEAR_ACTIVE_INTERRUPTS_PARAMETERS structure


## -description


The <b>GPIO_CLEAR_ACTIVE_INTERRUPTS_PARAMETERS</b> structure describes a set of general-purpose I/O (GPIO) interrupt pins to clear.


## -syntax


````
typedef struct _GPIO_CLEAR_ACTIVE_INTERRUPTS_PARAMETERS {
  BANK_ID BankId;
  ULONG64 ClearActiveMask;
  ULONG64 FailedClearMask;
} GPIO_CLEAR_ACTIVE_INTERRUPTS_PARAMETERS, *PGPIO_CLEAR_ACTIVE_INTERRUPTS_PARAMETERS;
````


## -struct-fields




### -field BankId

The identifier for the bank of GPIO pins that contains the pins to be cleared. If N is the number of banks in the GPIO controller, <b>BankId</b> is an integer in the range 0 to N–1. The GPIO framework extension (GpioClx) previously obtained the number of banks in the controller from the <a href="https://msdn.microsoft.com/library/windows/hardware/hh439399">CLIENT_QueryControllerBasicInformation</a> event callback function. For more information, see Remarks in <a href="https://msdn.microsoft.com/library/windows/hardware/hh439358">CLIENT_CONTROLLER_BASIC_INFORMATION</a>.


### -field ClearActiveMask

A 64-bit mask that indicates which interrupts to clear in the specified bank. A bit in the mask that is set to 1 identifies a pin that is configured as an interrupt and that is to be cleared. All other bits in the mask are 0. If N is the number of pins in this bank, the pins are numbered 0 to N–1. Bit 0 (the least significant bit) in the mask represents pin 0, bit 1 represents pin 1, and so on.


### -field FailedClearMask

A 64-bit mask that identifies the GPIO pins that could not be cleared. If the GPIO controller driver fails to clear a bit that is indicated in the <b>ClearActiveMask</b> member, the driver sets the corresponding bit in the <b>FailedClearMask</b> member to mark the failure. If all the bits specified in <b>ClearActiveMask</b> are successfully cleared, the driver sets <b>FailedClearMask</b> to zero.


## -remarks



The <i>ClearParameters</i> parameter of the <a href="https://msdn.microsoft.com/library/windows/hardware/hh439341">CLIENT_ClearActiveInterrupts</a> event callback function is a pointer to a caller-allocated <b>GPIO_CLEAR_ACTIVE_INTERRUPTS_PARAMETERS</b> structure. This function affects only GPIO pins that are configured as interrupt inputs and that are part of the specified bank of GPIO pins.




## -see-also

<a href="https://msdn.microsoft.com/library/windows/hardware/hh439399">CLIENT_QueryControllerBasicInformation</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh439341">CLIENT_ClearActiveInterrupts</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh439399">CLIENT_QueryControllerBasicInformation</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [GPIO\parports]:%20GPIO_CLEAR_ACTIVE_INTERRUPTS_PARAMETERS structure%20 RELEASE:%20(2/15/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

