---
UID: NS:gpioclx._GPIO_CLEAR_ACTIVE_INTERRUPTS_PARAMETERS
title: _GPIO_CLEAR_ACTIVE_INTERRUPTS_PARAMETERS (gpioclx.h)
description: The GPIO_CLEAR_ACTIVE_INTERRUPTS_PARAMETERS structure describes a set of general-purpose I/O (GPIO) interrupt pins to clear.
old-location: gpio\gpio_clear_active_interrupts_parameters.htm
tech.root: GPIO
ms.assetid: 71DC78B0-F987-4FFB-B3D0-E7AD88EECDA3
ms.date: 02/15/2018
ms.keywords: "*PGPIO_CLEAR_ACTIVE_INTERRUPTS_PARAMETERS, GPIO.gpio_clear_active_interrupts_parameters, GPIO_CLEAR_ACTIVE_INTERRUPTS_PARAMETERS, GPIO_CLEAR_ACTIVE_INTERRUPTS_PARAMETERS structure [Parallel Ports], PGPIO_CLEAR_ACTIVE_INTERRUPTS_PARAMETERS, PGPIO_CLEAR_ACTIVE_INTERRUPTS_PARAMETERS structure pointer [Parallel Ports], _GPIO_CLEAR_ACTIVE_INTERRUPTS_PARAMETERS, gpioclx/GPIO_CLEAR_ACTIVE_INTERRUPTS_PARAMETERS, gpioclx/PGPIO_CLEAR_ACTIVE_INTERRUPTS_PARAMETERS"
f1_keywords:
 - "gpioclx/GPIO_CLEAR_ACTIVE_INTERRUPTS_PARAMETERS"
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
req.irql: 
topic_type:
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- Gpioclx.h
api_name:
- GPIO_CLEAR_ACTIVE_INTERRUPTS_PARAMETERS
product:
- Windows
targetos: Windows
req.typenames: GPIO_CLEAR_ACTIVE_INTERRUPTS_PARAMETERS, *PGPIO_CLEAR_ACTIVE_INTERRUPTS_PARAMETERS
---

# _GPIO_CLEAR_ACTIVE_INTERRUPTS_PARAMETERS structure


## -description


The <b>GPIO_CLEAR_ACTIVE_INTERRUPTS_PARAMETERS</b> structure describes a set of general-purpose I/O (GPIO) interrupt pins to clear.


## -struct-fields




### -field BankId

The identifier for the bank of GPIO pins that contains the pins to be cleared. If N is the number of banks in the GPIO controller, <b>BankId</b> is an integer in the range 0 to N–1. The GPIO framework extension (GpioClx) previously obtained the number of banks in the controller from the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/gpioclx/nc-gpioclx-gpio_client_query_controller_basic_information">CLIENT_QueryControllerBasicInformation</a> event callback function. For more information, see Remarks in <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/gpioclx/ns-gpioclx-_client_controller_basic_information">CLIENT_CONTROLLER_BASIC_INFORMATION</a>.


### -field ClearActiveMask

A 64-bit mask that indicates which interrupts to clear in the specified bank. A bit in the mask that is set to 1 identifies a pin that is configured as an interrupt and that is to be cleared. All other bits in the mask are 0. If N is the number of pins in this bank, the pins are numbered 0 to N–1. Bit 0 (the least significant bit) in the mask represents pin 0, bit 1 represents pin 1, and so on.


### -field FailedClearMask

A 64-bit mask that identifies the GPIO pins that could not be cleared. If the GPIO controller driver fails to clear a bit that is indicated in the <b>ClearActiveMask</b> member, the driver sets the corresponding bit in the <b>FailedClearMask</b> member to mark the failure. If all the bits specified in <b>ClearActiveMask</b> are successfully cleared, the driver sets <b>FailedClearMask</b> to zero.


## -remarks



The <i>ClearParameters</i> parameter of the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/gpioclx/nc-gpioclx-gpio_client_clear_active_interrupts">CLIENT_ClearActiveInterrupts</a> event callback function is a pointer to a caller-allocated <b>GPIO_CLEAR_ACTIVE_INTERRUPTS_PARAMETERS</b> structure. This function affects only GPIO pins that are configured as interrupt inputs and that are part of the specified bank of GPIO pins.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/gpioclx/ns-gpioclx-_client_controller_basic_information">CLIENT_CONTROLLER_BASIC_INFORMATION</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/gpioclx/nc-gpioclx-gpio_client_clear_active_interrupts">CLIENT_ClearActiveInterrupts</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/gpioclx/nc-gpioclx-gpio_client_query_controller_basic_information">CLIENT_QueryControllerBasicInformation</a>
 

 

