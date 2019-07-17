---
UID: NE:uart.__unnamed_enum_0
title: UART_STATUS (uart.h)
description: Defines values for the status of a UART operation.
tech.root: serports
ms.assetid: 96750920-c761-499b-8ee9-39465e031d07
ms.date: 10/19/2018
ms.topic: enum
f1_keywords:
 - "uart/UART_STATUS"
ms.keywords: UART_STATUS, UART_STATUS, *PUART_STATUS,
req.header: uart.h
req.include-header:
req.target-type:
req.target-min-winverclnt: Windows 10, version 1803
req.target-min-winversvr:
req.kmdf-ver:
req.umdf-ver:
req.ddi-compliance:
req.max-support:
req.typenames: UART_STATUS, *PUART_STATUS
topic_type:
- apiref
api_type:
- HeaderDef
api_location:
- uart.h
api_name:
- UART_STATUS
product:
- Windows
targetos: Windows
---

# UART_STATUS enumeration

## -description

Defines values for the status of a UART operation.

## -enum-fields

### -field UartSuccess
The operation was successful, for example if data was available.

### -field UartNoData
No data is available, but not due to an error condition.

### -field UartError
A UART error such as overrun, parity, framing, etc.

### -field UartNotReady
The device is not ready.

## -remarks

## -see-also
