---
UID: NS:gpioclx._GPIO_READ_PINS_PARAMETERS
title: _GPIO_READ_PINS_PARAMETERS (gpioclx.h)
description: The GPIO_READ_PINS_PARAMETERS structure describes a read operation on a group of general-purpose I/O (GPIO) pins.
old-location: gpio\gpio_read_pins_parameters.htm
tech.root: GPIO
ms.assetid: D04C836E-C440-4AB9-BB44-7D1E8E0F681D
ms.date: 02/15/2018
keywords: ["GPIO_READ_PINS_PARAMETERS structure"]
ms.keywords: "*PGPIO_READ_PINS_PARAMETERS, GPIO.gpio_read_pins_parameters, GPIO_READ_PINS_PARAMETERS, GPIO_READ_PINS_PARAMETERS structure [Parallel Ports], PGPIO_READ_PINS_PARAMETERS, PGPIO_READ_PINS_PARAMETERS structure pointer [Parallel Ports], _GPIO_READ_PINS_PARAMETERS, gpioclx/GPIO_READ_PINS_PARAMETERS, gpioclx/PGPIO_READ_PINS_PARAMETERS"
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
req.typenames: GPIO_READ_PINS_PARAMETERS, *PGPIO_READ_PINS_PARAMETERS
f1_keywords:
 - _GPIO_READ_PINS_PARAMETERS
 - gpioclx/_GPIO_READ_PINS_PARAMETERS
 - PGPIO_READ_PINS_PARAMETERS
 - gpioclx/PGPIO_READ_PINS_PARAMETERS
 - GPIO_READ_PINS_PARAMETERS
 - gpioclx/GPIO_READ_PINS_PARAMETERS
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - Gpioclx.h
api_name:
 - GPIO_READ_PINS_PARAMETERS
---

# _GPIO_READ_PINS_PARAMETERS structure


## -description

The <b>GPIO_READ_PINS_PARAMETERS</b> structure describes a read operation on a group of general-purpose I/O (GPIO) pins.

## -struct-fields

### -field BankId

The identifier for the bank of GPIO pins that contains the pins to read. If N is the number of banks in the GPIO controller, <b>BankId</b> is an integer in the range 0 to N–1. The GPIO framework extension (GpioClx) previously obtained the number of banks in the controller from the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/gpioclx/nc-gpioclx-gpio_client_query_controller_basic_information">CLIENT_QueryControllerBasicInformation</a> event callback function. For more information, see Remarks in <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/gpioclx/ns-gpioclx-_client_controller_basic_information">CLIENT_CONTROLLER_BASIC_INFORMATION</a>.

### -field PinNumberTable

A pointer to an array of bank-relative PIN_NUMBER values. Each array element specifies the number of a GPIO pin to read from. If this bank has N pins, the pins are numbered 0 to N–1. The number of elements in this array is specified by the <b>PinCount</b> member.

### -field PinCount

The number of elements in the <b>PinNumberTable</b> array.

### -field Buffer

A pointer to a buffer to hold the values that the GPIO controller driver reads from the GPIO pins that are specified by the <b>PinNumberTable</b> array. Array element 0 specifies the GPIO pin whose value is saved to bit 0 (the least significant bit) in the buffer, array element 1 specifies the GPIO pin whose value is saved to bit 1 in the buffer, and so on.

### -field Flags

A set of flags to control the GPIO pin read operation. If the <b>WriteConfiguredPins</b> flag bit is set, the GPIO controller driver can read from a GPIO pin that is configured for write operations.

### -field Reserved

Reserved for system use.

## -remarks

The <i>ReadParameters</i> parameter of the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/gpioclx/nc-gpioclx-gpio_client_read_pins">CLIENT_ReadGpioPins</a> event callback function is a pointer to a caller-allocated <b>GPIO_READ_PINS_PARAMETERS</b> structure. All of the pins that this function reads are part of the same bank of GPIO pins.

## -see-also

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/gpioclx/ns-gpioclx-_client_controller_basic_information">CLIENT_CONTROLLER_BASIC_INFORMATION</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/gpioclx/nc-gpioclx-gpio_client_query_controller_basic_information">CLIENT_QueryControllerBasicInformation</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/gpioclx/nc-gpioclx-gpio_client_read_pins">CLIENT_ReadGpioPins</a>

