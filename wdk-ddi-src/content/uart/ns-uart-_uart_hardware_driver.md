---
UID: NS:uart._UART_HARDWARE_DRIVER
title: _UART_HARDWARE_DRIVER (uart.h)
description: Contains function pointers for interacting with a specific type of UART hardware.
tech.root: serports
ms.assetid: 8c521dda-f906-44a8-b0cc-283bd1afacf6
ms.date: 10/19/2018
f1_keywords:
 - "uart/_UART_HARDWARE_DRIVER"
ms.keywords: _UART_HARDWARE_DRIVER, UART_HARDWARE_DRIVER, *PUART_HARDWARE_DRIVER,
req.header: uart.h
req.include-header:
req.target-type:
req.target-min-winverclnt: Windows 10, version 1803
req.target-min-winversvr:
req.kmdf-ver:
req.umdf-ver:
req.lib:
req.dll:
req.ddi-compliance:
req.unicode-ansi:
req.max-support:
req.typenames: UART_HARDWARE_DRIVER, *PUART_HARDWARE_DRIVER
topic_type:
- apiref
api_type:
- HeaderDef
api_location:
- uart.h
api_name:
- _UART_HARDWARE_DRIVER
product:
- Windows
targetos: Windows
---

# _UART_HARDWARE_DRIVER structure

## -description
Contains function pointers for interacting with a specific type of UART hardware. Generally, there should be one instance of this structure for each supported hardware device. The function pointers are not expected to change at runtime.

## -struct-fields

### -field InitializePort
A pointer to a [**UART_INITIALIZE_PORT**](nc-uart-uart_initialize_port.md) callback function to initialize/reset the UART hardware. This function must be called before calling any other driver functions.

### -field SetBaud
A pointer to a [**UART_SET_BAUD**](ns-uart-_uart_hardware_driver.md) callback function that sets the baud rate of the UART hardware to the specified value.

### -field GetByte
A pointer to a [**UART_GET_BYTE**](nc-uart-uart_get_byte.md) callback function that reads a byte from the UART device.

### -field PutByte
A pointer to a [**UART_PUT_BYTE**](nc-uart-uart_put_byte.md) callback function that writes a byte to the UART device.

### -field RxReady
A pointer to a [**UART_RX_READY**](nc-uart-uart_rx_ready.md) callback function that determines whether there is data pending in the UART hardware.

## -remarks

## -see-also
