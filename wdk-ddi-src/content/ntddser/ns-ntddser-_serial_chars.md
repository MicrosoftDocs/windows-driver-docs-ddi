---
UID: NS:ntddser._SERIAL_CHARS
title: _SERIAL_CHARS (ntddser.h)
description: The SERIAL_CHARS structure specifies the special characters that the serial controller driver uses for handshake flow control.
old-location: serports\serial_chars.htm
tech.root: serports
ms.assetid: D9146B9F-5AE4-436B-B223-0A61400FE9AC
ms.date: 04/23/2018
keywords: ["_SERIAL_CHARS structure"]
ms.keywords: "*PSERIAL_CHARS, PSERIAL_CHARS, PSERIAL_CHARS structure pointer [Serial Ports], SERIAL_CHARS, SERIAL_CHARS structure [Serial Ports], _SERIAL_CHARS, ntddser/PSERIAL_CHARS, ntddser/SERIAL_CHARS, serports.serial_chars"
f1_keywords:
 - "ntddser/SERIAL_CHARS"
req.header: ntddser.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: 
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
- Ntddser.h
api_name:
- SERIAL_CHARS
product:
- Windows
targetos: Windows
req.typenames: SERIAL_CHARS, *PSERIAL_CHARS
---

# _SERIAL_CHARS structure


## -description


The <b>SERIAL_CHARS</b> structure specifies the special characters that the serial controller driver uses for handshake flow control.


## -struct-fields




### -field EofChar

The EOF (end of file) character. Receipt of this character marks the end of the input stream.


### -field ErrorChar

The parity error replacement character. Bytes received with parity errors are replaced by this character.


### -field BreakChar

The break character. Receipt of this character indicates that a break (temporary pause) occurred in the input stream.


### -field EventChar

The event character. Receipt of this character signals a serial communication event if the SERIAL_EV_RXFLAG flag bit is set in the current wait mask. The wait mask is set by the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddser/ni-ntddser-ioctl_serial_set_wait_mask">IOCTL_SERIAL_SET_WAIT_MASK</a> request. The <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddser/ni-ntddser-ioctl_serial_wait_on_mask">IOCTL_SERIAL_WAIT_ON_MASK</a> request initiates a wait for the events in the wait mask.


### -field XonChar

The XON (transmit on) character to use for both transmit and receive operations. The XON and XOFF characters are used for software flow control.


### -field XoffChar

The XOFF (transmit off) character to use for both transmit and receive operations.


## -remarks



This structure is used by the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddser/ni-ntddser-ioctl_serial_set_chars">IOCTL_SERIAL_SET_CHARS</a> and <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddser/ni-ntddser-ioctl_serial_get_chars">IOCTL_SERIAL_GET_CHARS</a> requests.

An <b>IOCTL_SERIAL_SET_CHARS</b> request to set the XON and XOFF characters to the same value will fail.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddser/ni-ntddser-ioctl_serial_get_chars">IOCTL_SERIAL_GET_CHARS</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddser/ni-ntddser-ioctl_serial_set_chars">IOCTL_SERIAL_SET_CHARS</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddser/ni-ntddser-ioctl_serial_set_wait_mask">IOCTL_SERIAL_SET_WAIT_MASK</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddser/ni-ntddser-ioctl_serial_wait_on_mask">IOCTL_SERIAL_WAIT_ON_MASK</a>
 

 

