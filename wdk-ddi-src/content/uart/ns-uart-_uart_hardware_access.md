---
UID: NS:uart._UART_HARDWARE_ACCESS
title: _UART_HARDWARE_ACCESS (uart.h)
description: Contains I/O functions and the function pointers used by the serial drivers to access the device hardware.
tech.root: serports
ms.assetid: c666e70b-c456-4fb8-baa7-487936801181
ms.date: 10/19/2018
keywords: ["_UART_HARDWARE_ACCESS structure"]
f1_keywords:
 - "uart/_UART_HARDWARE_ACCESS"
 - "_UART_HARDWARE_ACCESS"
ms.keywords: _UART_HARDWARE_ACCESS, UART_HARDWARE_ACCESS, *PUART_HARDWARE_ACCESS,
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
req.typenames: UART_HARDWARE_ACCESS, *PUART_HARDWARE_ACCESS
topic_type:
- apiref
api_type:
- HeaderDef
api_location:
- uart.h
api_name:
- _UART_HARDWARE_ACCESS
targetos: Windows
---

# _UART_HARDWARE_ACCESS structure

## -description
I/O functions and the function pointers used by the serial drivers to access the device hardware.

## -struct-fields

### -field ReadPort8
A pointer to a [**UART_HARDWARE_READ_UCHAR**](nc-uart-uart_hardware_read_uchar.md) callback function that reads from a port.

### -field WritePort8
A pointer to a [**UART_HARDWARE_WRITE_UCHAR**](nc-uart-uart_hardware_write_uchar.md) callback function that writes to a port.

### -field ReadPort16
A pointer to a [**UART_HARDWARE_READ_USHORT**](nc-uart-uart_hardware_read_ushort.md) callback function that reads from a port.

### -field WritePort16
A pointer to a [**UART_HARDWARE_WRITE_USHORT**](nc-uart-uart_hardware_write_ushort.md) callback function that writes to a port.

### -field ReadPort32
A pointer to a [**UART_HARDWARE_READ_ULONG**](nc-uart-uart_hardware_read_ulong.md) callback function that reads from a port.

### -field WritePort32
A pointer to a [**UART_HARDWARE_WRITE_ULONG**](nc-uart-uart_hardware_write_ulong.md) callback function that writers to a port.

### -field ReadRegister8
A pointer to a [**UART_HARDWARE_READ_UCHAR**](nc-uart-uart_hardware_read_uchar.md) callback function that reads from a register.

### -field WriteRegister8
A pointer to a [**UART_HARDWARE_READ_UCHAR**](nc-uart-uart_hardware_read_uchar.md) callback function that writes to a register.

### -field ReadRegister16
A pointer to a [**UART_HARDWARE_READ_USHORT**](nc-uart-uart_hardware_read_ushort.md) callback function that reads from a register.

### -field WriteRegister16
A pointer to a [**UART_HARDWARE_WRITE_USHORT**](nc-uart-uart_hardware_write_ushort.md) callback function that writes to a register.

### -field ReadRegister32
A pointer to a [**UART_HARDWARE_READ_ULONG**](nc-uart-uart_hardware_read_ulong.md) callback function that reads from a register.

### -field WriteRegister32
A pointer to a [**UART_HARDWARE_WRITE_ULONG**](nc-uart-uart_hardware_write_ulong.md) callback function that writes to a register.

### -field ReadRegister64
A pointer to a [**UART_HARDWARE_READ_ULONG64**](nc-uart-uart_hardware_read_ulong64.md) callback function that reads from the specified register.

### -field WriteRegister64
A pointer to a [**UART_HARDWARE_WRITE_ULONG64**](nc-uart-uart_hardware_write_ulong64.md) callback function that writes to the specified register.


## -remarks

## -see-also
