---
UID: NS:gpioclx._GPIO_READ_PINS_MASK_PARAMETERS
title: _GPIO_READ_PINS_MASK_PARAMETERS (gpioclx.h)
description: The GPIO_READ_PINS_MASK_PARAMETERS structure describes a read operation on a bank of general-purpose I/O (GPIO) pins.
old-location: gpio\gpio_read_pins_mask_parameters.htm
tech.root: GPIO
ms.assetid: 679C9A71-7F39-4344-93D0-6B1332D76CF7
ms.date: 02/15/2018
ms.keywords: "*PGPIO_READ_PINS_MASK_PARAMETERS, GPIO.gpio_read_pins_mask_parameters, GPIO_READ_PINS_MASK_PARAMETERS, GPIO_READ_PINS_MASK_PARAMETERS structure [Parallel Ports], PGPIO_READ_PINS_MASK_PARAMETERS, PGPIO_READ_PINS_MASK_PARAMETERS structure pointer [Parallel Ports], _GPIO_READ_PINS_MASK_PARAMETERS, gpioclx/GPIO_READ_PINS_MASK_PARAMETERS, gpioclx/PGPIO_READ_PINS_MASK_PARAMETERS"
ms.topic: struct
f1_keywords:
 - "gpioclx/GPIO_READ_PINS_MASK_PARAMETERS"
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
- GPIO_READ_PINS_MASK_PARAMETERS
product:
- Windows
targetos: Windows
req.typenames: GPIO_READ_PINS_MASK_PARAMETERS, *PGPIO_READ_PINS_MASK_PARAMETERS
---

# _GPIO_READ_PINS_MASK_PARAMETERS structure


## -description


The <b>GPIO_READ_PINS_MASK_PARAMETERS</b> structure describes a read operation on a bank of general-purpose I/O (GPIO) pins.


## -struct-fields




### -field BankId

The identifier for this bank of GPIO pins. If N is the number of banks in the GPIO controller, <b>BankId</b> is an integer in the range 0 to N–1. The GPIO framework extension (GpioClx) previously obtained the number of banks in the controller from the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/gpioclx/nc-gpioclx-gpio_client_query_controller_basic_information">CLIENT_QueryControllerBasicInformation</a> event callback function. For more information, see Remarks in <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/gpioclx/ns-gpioclx-_client_controller_basic_information">CLIENT_CONTROLLER_BASIC_INFORMATION</a>.


### -field PinValues

A 64-bit variable to which the GPIO controller driver stores the values that it reads from the GPIO pins in the bank. If N is the number of GPIO pins in this bank, the pins are numbered 0 to N–1. The value from pin number 0 is saved in bit 0 (the least significant bit) of this variable, the value from pin number 1 is saved in bit 1 of this variable, and so on.


### -field Flags

A set of flags to control the GPIO pin read operation. If the <b>WriteConfiguredPins</b> flag bit is set, the GPIO controller driver can read from a GPIO pin that is configured for write operations.


### -field Reserved

Reserved for system use.


## -remarks



The <i>ReadParameters</i> parameter of the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/gpioclx/nc-gpioclx-gpio_client_read_pins_mask">CLIENT_ReadGpioPinsUsingMask</a> event callback function is a pointer to a caller-allocated <b>GPIO_READ_PINS_MASK_PARAMETERS</b> structure.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/gpioclx/ns-gpioclx-_client_controller_basic_information">CLIENT_CONTROLLER_BASIC_INFORMATION</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/gpioclx/nc-gpioclx-gpio_client_query_controller_basic_information">CLIENT_QueryControllerBasicInformation</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/gpioclx/nc-gpioclx-gpio_client_read_pins_mask">CLIENT_ReadGpioPinsUsingMask</a>
 

 

