---
UID: NS:gpioclx._GPIO_QUERY_ACTIVE_INTERRUPTS_PARAMETERS
title: _GPIO_QUERY_ACTIVE_INTERRUPTS_PARAMETERS (gpioclx.h)
description: The GPIO_QUERY_ACTIVE_INTERRUPTS_PARAMETERS structure describes a set of general-purpose I/O (GPIO) interrupt pins to query for their enabled and active states.
old-location: gpio\gpio_query_active_interrupts_parameters.htm
tech.root: GPIO
ms.assetid: A3111B9C-319F-4560-B5A9-5CA6523AD935
ms.date: 02/15/2018
keywords: ["GPIO_QUERY_ACTIVE_INTERRUPTS_PARAMETERS structure"]
ms.keywords: "*PGPIO_QUERY_ACTIVE_INTERRUPTS_PARAMETERS, GPIO.gpio_query_active_interrupts_parameters, GPIO_QUERY_ACTIVE_INTERRUPTS_PARAMETERS, GPIO_QUERY_ACTIVE_INTERRUPTS_PARAMETERS structure [Parallel Ports], PGPIO_QUERY_ACTIVE_INTERRUPTS_PARAMETERS, PGPIO_QUERY_ACTIVE_INTERRUPTS_PARAMETERS structure pointer [Parallel Ports], _GPIO_QUERY_ACTIVE_INTERRUPTS_PARAMETERS, gpioclx/GPIO_QUERY_ACTIVE_INTERRUPTS_PARAMETERS, gpioclx/PGPIO_QUERY_ACTIVE_INTERRUPTS_PARAMETERS"
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
targetos: Windows
req.typenames: GPIO_QUERY_ACTIVE_INTERRUPTS_PARAMETERS, *PGPIO_QUERY_ACTIVE_INTERRUPTS_PARAMETERS
f1_keywords:
 - _GPIO_QUERY_ACTIVE_INTERRUPTS_PARAMETERS
 - gpioclx/_GPIO_QUERY_ACTIVE_INTERRUPTS_PARAMETERS
 - PGPIO_QUERY_ACTIVE_INTERRUPTS_PARAMETERS
 - gpioclx/PGPIO_QUERY_ACTIVE_INTERRUPTS_PARAMETERS
 - GPIO_QUERY_ACTIVE_INTERRUPTS_PARAMETERS
 - gpioclx/GPIO_QUERY_ACTIVE_INTERRUPTS_PARAMETERS
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - Gpioclx.h
api_name:
 - GPIO_QUERY_ACTIVE_INTERRUPTS_PARAMETERS
---

# _GPIO_QUERY_ACTIVE_INTERRUPTS_PARAMETERS structure


## -description

The <b>GPIO_QUERY_ACTIVE_INTERRUPTS_PARAMETERS</b> structure describes a set of general-purpose I/O (GPIO) interrupt pins to query for their enabled and active states.

## -struct-fields

### -field BankId

The identifier for the bank of GPIO pins that contains the interrupts to query. If N is the number of banks in the GPIO controller, <b>BankId</b> is an integer in the range 0 to N–1. The GPIO framework extension (GpioClx) previously obtained the number of banks in the controller from the <a href="/windows-hardware/drivers/ddi/gpioclx/nc-gpioclx-gpio_client_query_controller_basic_information">CLIENT_QueryControllerBasicInformation</a> event callback function. For more information, see Remarks in <a href="/windows-hardware/drivers/ddi/gpioclx/ns-gpioclx-_client_controller_basic_information">CLIENT_CONTROLLER_BASIC_INFORMATION</a>.

### -field EnabledMask

A ULONG64 variable to which the GPIO controller driver writes a 64-bit mask to indicate which interrupt pins are enabled in the specified bank. A bit in the mask that is set to 1 identifies a pin that is configured as an interrupt and that is enabled. All other bits in the mask are 0. If N is the number of pins in this bank, the pins are numbered 0 to N–1. Bit 0 (the least significant bit) in the mask represents pin 0, bit 1 represents pin 1, and so on.

### -field ActiveMask

A ULONG64 variable to which the GPIO controller driver writes a 64-bit mask to indicate which interrupt pins are active in the specified bank. A bit in the mask that is set to 1 identifies a pin that is configured as an interrupt and that is active. All other bits in the mask are 0.

## -remarks

The <i>QueryActiveParameters</i> parameter of the <a href="/windows-hardware/drivers/ddi/gpioclx/nc-gpioclx-gpio_client_query_active_interrupts">CLIENT_QueryActiveInterrupts</a> event callback function is a pointer to a caller-allocated <b>GPIO_QUERY_ACTIVE_INTERRUPTS_PARAMETERS</b> structure. This function queries only GPIO pins that are configured as interrupt inputs. All other GPIO pins in the specified bank are represented as zeros in the <b>EnabledMask</b> and <b>ActiveMask</b> members of the structure.

## -see-also

<a href="/windows-hardware/drivers/ddi/gpioclx/ns-gpioclx-_client_controller_basic_information">CLIENT_CONTROLLER_BASIC_INFORMATION</a>



<a href="/windows-hardware/drivers/ddi/gpioclx/nc-gpioclx-gpio_client_query_active_interrupts">CLIENT_QueryActiveInterrupts</a>



<a href="/windows-hardware/drivers/ddi/gpioclx/nc-gpioclx-gpio_client_query_controller_basic_information">CLIENT_QueryControllerBasicInformation</a>