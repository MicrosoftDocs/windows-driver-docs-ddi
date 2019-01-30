---
UID: NS:gpioclx._GPIO_QUERY_ENABLED_INTERRUPTS_PARAMETERS
title: "_GPIO_QUERY_ENABLED_INTERRUPTS_PARAMETERS" (gpioclx.h)
description: The GPIO_QUERY_ENABLED_INTERRUPTS_PARAMETERS structure indicates which interrupt pins in a bank of general-purpose I/O (GPIO) pins are enabled.
old-location: gpio\gpio_query_enabled_interrupts_parameters.htm
tech.root: GPIO
ms.assetid: CC2EEF26-CCC0-4093-8A44-12FF1EDD2FF9
ms.date: 02/15/2018
ms.keywords: "*PGPIO_QUERY_ENABLED_INTERRUPTS_PARAMETERS, GPIO.gpio_query_enabled_interrupts_parameters, GPIO_QUERY_ENABLED_INTERRUPTS_PARAMETERS, GPIO_QUERY_ENABLED_INTERRUPTS_PARAMETERS structure [Parallel Ports], PGPIO_QUERY_ENABLED_INTERRUPTS_PARAMETERS, PGPIO_QUERY_ENABLED_INTERRUPTS_PARAMETERS structure pointer [Parallel Ports], _GPIO_QUERY_ENABLED_INTERRUPTS_PARAMETERS, gpioclx/GPIO_QUERY_ENABLED_INTERRUPTS_PARAMETERS, gpioclx/PGPIO_QUERY_ENABLED_INTERRUPTS_PARAMETERS"
ms.topic: struct
req.header: gpioclx.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: Supported starting with Windows 8.1.
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
req.irql: 
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	Gpioclx.h
api_name:
-	GPIO_QUERY_ENABLED_INTERRUPTS_PARAMETERS
product:
- Windows
targetos: Windows
req.typenames: GPIO_QUERY_ENABLED_INTERRUPTS_PARAMETERS, *PGPIO_QUERY_ENABLED_INTERRUPTS_PARAMETERS
---

# _GPIO_QUERY_ENABLED_INTERRUPTS_PARAMETERS structure


## -description


The <b>GPIO_QUERY_ENABLED_INTERRUPTS_PARAMETERS</b> structure indicates which interrupt pins in a bank of general-purpose I/O (GPIO) pins are enabled.


## -struct-fields




### -field BankId

The identifier for the bank of GPIO pins to query for enabled interrupts. If N is the number of banks in the GPIO controller, <b>BankId</b> is an integer in the range 0 to N–1. The GPIO framework extension (GpioClx) previously obtained the number of banks in the controller from the <a href="https://msdn.microsoft.com/library/windows/hardware/hh439399">CLIENT_QueryControllerBasicInformation</a> event callback function. For more information, see Remarks in <a href="https://msdn.microsoft.com/library/windows/hardware/hh439358">CLIENT_CONTROLLER_BASIC_INFORMATION</a>.


### -field EnabledMask

A 64-bit mask that indicates which interrupts are enabled in the specified bank. A bit in the mask that is set to 1 identifies an interrupt pin that is enabled for interrupts. All other bits in the mask are 0. If N is the number of pins in this bank, the pins are numbered 0 to N–1. Bit 0 (the least significant bit) in the mask represents pin 0, bit 1 represents pin 1, and so on.


## -remarks



The <i>QueryEnabledParameters</i> parameter of the <a href="https://msdn.microsoft.com/library/windows/hardware/dn265184">CLIENT_QueryEnabledInterrupts</a> event callback function is a pointer to a caller-allocated <b>GPIO_QUERY_ENABLED_INTERRUPTS_PARAMETERS</b> structure. Before calling this function, the caller writes a bank ID to the <b>BankId</b> member of this structure to specify which bank of GPIO pins to query. The function writes a mask value to the <b>EnabledMask</b> member of this structure to indicate which interrupts are enabled in the specified bank.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/hh439358">CLIENT_CONTROLLER_BASIC_INFORMATION</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh439399">CLIENT_QueryControllerBasicInformation</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/dn265184">CLIENT_QueryEnabledInterrupts</a>
 

 

