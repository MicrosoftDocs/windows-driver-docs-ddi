---
UID: NE:gpioclx._GPIO_CONNECT_IO_PINS_MODE
title: _GPIO_CONNECT_IO_PINS_MODE (gpioclx.h)
description: The GPIO_CONNECT_IO_PINS_MODE enumeration indicates whether a set of general-purpose I/O (GPIO) pins is configured as inputs or outputs.
old-location: gpio\gpio_connect_io_pins_mode.htm
tech.root: GPIO
ms.assetid: 17E98D35-8C63-4EEC-B8DD-896FA2B084A8
ms.date: 02/15/2018
keywords: ["_GPIO_CONNECT_IO_PINS_MODE enumeration"]
ms.keywords: "*PGPIO_CONNECT_IO_PINS_MODE, ConnectModeInput, ConnectModeInvalid, ConnectModeMaximum, ConnectModeOutput, GPIO.gpio_connect_io_pins_mode, GPIO_CONNECT_IO_PINS_MODE, GPIO_CONNECT_IO_PINS_MODE enumeration [Parallel Ports], _GPIO_CONNECT_IO_PINS_MODE, gpioclx/ConnectModeInput, gpioclx/ConnectModeInvalid, gpioclx/ConnectModeMaximum, gpioclx/ConnectModeOutput, gpioclx/GPIO_CONNECT_IO_PINS_MODE"
f1_keywords:
 - "gpioclx/GPIO_CONNECT_IO_PINS_MODE"
 - "GPIO_CONNECT_IO_PINS_MODE"
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
- GPIO_CONNECT_IO_PINS_MODE
product:
- Windows
targetos: Windows
req.typenames: GPIO_CONNECT_IO_PINS_MODE, *PGPIO_CONNECT_IO_PINS_MODE
---

# _GPIO_CONNECT_IO_PINS_MODE enumeration


## -description


The <b>GPIO_CONNECT_IO_PINS_MODE</b> enumeration indicates whether a set of general-purpose I/O (GPIO) pins is configured as inputs or outputs.


## -enum-fields




### -field ConnectModeInvalid

The connection mode (input or output) for this set of GPIO pins is uninitialized.


### -field ConnectModeInput

This set of GPIO pins is configured as data inputs.


### -field ConnectModeOutput

This set of GPIO pins is configured as data outputs.


### -field ConnectModeMaximum

The maximum value in the enumeration.


## -remarks



The <b>ConnectMode</b> member of the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/gpioclx/ns-gpioclx-_gpio_connect_io_pins_parameters">GPIO_CONNECT_IO_PINS_PARAMETERS</a> structure contains a <b>GPIO_CONNECT_IO_PINS_MODE</b> enumeration constant.

The <b>ConnectModeInput</b> enumeration constant labels a set of GPIO pins that can be read by an <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/gpio/ni-gpio-ioctl_gpio_read_pins">IOCTL_GPIO_READ_PINS</a> request. <b>ConnectModeOutput</b> labels a set of GPIO pins that can be written to by an <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/gpio/ni-gpio-ioctl_gpio_write_pins">IOCTL_GPIO_WRITE_PINS</a> request.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/gpioclx/ns-gpioclx-_gpio_connect_io_pins_parameters">GPIO_CONNECT_IO_PINS_PARAMETERS</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/gpio/ni-gpio-ioctl_gpio_read_pins">IOCTL_GPIO_READ_PINS</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/gpio/ni-gpio-ioctl_gpio_write_pins">IOCTL_GPIO_WRITE_PINS</a>
 

 

