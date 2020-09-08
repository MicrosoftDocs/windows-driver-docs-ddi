---
UID: NS:gpioclx._GPIO_DISCONNECT_IO_PINS_PARAMETERS
title: _GPIO_DISCONNECT_IO_PINS_PARAMETERS (gpioclx.h)
description: The GPIO_DISCONNECT_IO_PINS_PARAMETERS structure describes a set of general-purpose I/O (GPIO) pins that are to be disconnected.
old-location: gpio\gpio_disconnect_io_pins_parameters.htm
tech.root: GPIO
ms.assetid: 79ABCF93-4EC3-49D5-9943-C820B0B8CF66
ms.date: 02/15/2018
keywords: ["GPIO_DISCONNECT_IO_PINS_PARAMETERS structure"]
ms.keywords: "*PGPIO_DISCONNECT_IO_PINS_PARAMETERS, GPIO.gpio_disconnect_io_pins_parameters, GPIO_DISCONNECT_IO_PINS_PARAMETERS, GPIO_DISCONNECT_IO_PINS_PARAMETERS structure [Parallel Ports], PGPIO_DISCONNECT_IO_PINS_PARAMETERS, PGPIO_DISCONNECT_IO_PINS_PARAMETERS structure pointer [Parallel Ports], _GPIO_DISCONNECT_IO_PINS_PARAMETERS, gpioclx/GPIO_DISCONNECT_IO_PINS_PARAMETERS, gpioclx/PGPIO_DISCONNECT_IO_PINS_PARAMETERS"
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
req.typenames: GPIO_DISCONNECT_IO_PINS_PARAMETERS, *PGPIO_DISCONNECT_IO_PINS_PARAMETERS
f1_keywords:
 - _GPIO_DISCONNECT_IO_PINS_PARAMETERS
 - gpioclx/_GPIO_DISCONNECT_IO_PINS_PARAMETERS
 - PGPIO_DISCONNECT_IO_PINS_PARAMETERS
 - gpioclx/PGPIO_DISCONNECT_IO_PINS_PARAMETERS
 - GPIO_DISCONNECT_IO_PINS_PARAMETERS
 - gpioclx/GPIO_DISCONNECT_IO_PINS_PARAMETERS
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - Gpioclx.h
api_name:
 - GPIO_DISCONNECT_IO_PINS_PARAMETERS
---

# _GPIO_DISCONNECT_IO_PINS_PARAMETERS structure


## -description

The <b>GPIO_DISCONNECT_IO_PINS_PARAMETERS</b> structure describes a set of general-purpose I/O (GPIO) pins that are to be disconnected.

## -struct-fields

### -field BankId

The identifier for the bank that contains the GPIO pins. If M is the number of banks in the GPIO controller, <b>BankId</b> is an integer in the range 0 to M–1. The GPIO framework extension (GpioClx) previously obtained the number of banks in the controller from the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/gpioclx/nc-gpioclx-gpio_client_query_controller_basic_information">CLIENT_QueryControllerBasicInformation</a> event callback function. For more information, see Remarks in <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/gpioclx/ns-gpioclx-_client_controller_basic_information">CLIENT_CONTROLLER_BASIC_INFORMATION</a>.

### -field PinNumberTable

A pointer to an array of PIN_NUMBER values. Each array element specifies the number of a GPIO pin to disconnect from. If the GPIO controller has N pins, the pins are numbered 0 to N–1. The number of elements in this array is specified by the <b>PinCount</b> member.

### -field PinCount

The number of elements in the <b>PinNumberTable</b> array.

### -field DisconnectMode

Whether the GPIO pins in the connection that is being closed are configured as inputs or as outputs. The value of this member is <b>ConnectModeInput</b> for a read-only connection, <b>ConnectModeOutput</b> for a write-only connection, or (<b>ConnectModeInput</b> | <b>ConnectModeOutput</b>) for a read/write connection. For more information, see <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/gpioclx/ne-gpioclx-_gpio_connect_io_pins_mode">GPIO_CONNECT_IO_PINS_MODE</a>.

### -field DisconnectFlags

A set of flags that control how the GPIO pins are to be configured after they are closed. If the <b>PreserveConfiguration</b> flag bit is set, the GPIO controller driver preserves the configuration of the pins after they are disconnected. For more information, see Remarks.

## -remarks

The <i>DisconnectParameters</i> parameter to the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/gpioclx/nc-gpioclx-gpio_client_disconnect_io_pins">CLIENT_DisconnectIoPins</a> event callback routine is a pointer to a <b>GPIO_CONNECT_IO_PINS_PARAMETERS</b> structure.

By default, when a GPIO I/O pin is disconnected, the GPIO controller driver configures the pin in a platform-specific initial state. The pin is typically configured in a low-power state to reduce the load on the battery. However, the <b>PreserveConfiguration</b> flag can be used to override this default behavior. The flag tells the GPIO controller driver to preserve the configuration of the I/O pins that are being disconnected.

For example, a peripheral device driver might open a logical connection to a GPIO I/O pin that is configured as an output, and then write a bit value of 1 to the pin. The <b>PreserveConfiguration</b> flag enables the driver to close the connection without altering the pin's output level. Later, if the driver needs to change the output level of the pin from 1 to 0, the driver opens a new connection to the pin.

## -see-also

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/gpioclx/ns-gpioclx-_client_controller_basic_information">CLIENT_CONTROLLER_BASIC_INFORMATION</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/gpioclx/nc-gpioclx-gpio_client_disconnect_io_pins">CLIENT_DisconnectIoPins</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/gpioclx/nc-gpioclx-gpio_client_query_controller_basic_information">CLIENT_QueryControllerBasicInformation</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/gpioclx/ne-gpioclx-_gpio_connect_io_pins_mode">GPIO_CONNECT_IO_PINS_MODE</a>

