---
UID: NS:uart._CPPORT
title: _CPPORT
description: Contains the mutable runtime state of a specific instance of a UART device.
tech.root: serports
ms.assetid: f82a2ac1-ed30-4e75-ad87-54275a36130b
ms.date: 10/19/2018
ms.topic: struct
ms.keywords: _CPPORT, CPPORT, *PCPPORT,
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
req.typenames: CPPORT, *PCPPORT
topic_type:
-	apiref
api_type:
-	HeaderDef
api_location:
-	uart.h
api_name:
-	_CPPORT
product:
-	Windows
targetos: Windows
---

# _CPPORT structure

## -description
Contains the mutable runtime state of a specific instance of a UART device.

## -struct-fields

### -field Address
The base address of the UART registers.

### -field BaudRate
The UART hardware's baud rate in bits per second.

### -field Flags
A bitmask of the port's internal flags.

### -field ByteWidth
The width of each of the UART hardware's registers as a number of bytes.

### -field Read
A pointer to a [**UART_HARDWARE_READ_INDEXED_UCHAR**](nc-uart-uart_hardware_read_indexed_uchar.md) callback function used to read from a register on the UART hardware.

### -field Write
A pointer to a [**UART_HARDWARE_WRITE_INDEXED_UCHAR**](nc-uart-uart_hardware_write_indexed_uchar.md) callback function used to write to a register on the UART hardware.

## -remarks

## -see-also
