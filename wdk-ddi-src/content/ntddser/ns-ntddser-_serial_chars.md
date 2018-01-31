---
UID: NS:ntddser._SERIAL_CHARS
title: "_SERIAL_CHARS"
author: windows-driver-content
description: The SERIAL_CHARS structure specifies the special characters that the serial controller driver uses for handshake flow control.
old-location: serports\serial_chars.htm
old-project: serports
ms.assetid: D9146B9F-5AE4-436B-B223-0A61400FE9AC
ms.author: windowsdriverdev
ms.date: 12/14/2017
ms.keywords: "*PSERIAL_CHARS, _SERIAL_CHARS, PSERIAL_CHARS, SERIAL_CHARS, ntddser/SERIAL_CHARS, PSERIAL_CHARS structure pointer [Serial Ports], SERIAL_CHARS structure [Serial Ports], ntddser/PSERIAL_CHARS, serports.serial_chars"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	Ntddser.h
apiname:
-	SERIAL_CHARS
product: Windows
targetos: Windows
req.typenames: SERIAL_CHARS, *PSERIAL_CHARS
---

# _SERIAL_CHARS structure


## -description


The <b>SERIAL_CHARS</b> structure specifies the special characters that the serial controller driver uses for handshake flow control.


## -syntax


````
typedef struct _SERIAL_CHARS {
  UCHAR EofChar;
  UCHAR ErrorChar;
  UCHAR BreakChar;
  UCHAR EventChar;
  UCHAR XonChar;
  UCHAR XoffChar;
} SERIAL_CHARS, *PSERIAL_CHARS;
````


## -struct-fields




#### - EofChar

The EOF (end of file) character. Receipt of this character marks the end of the input stream.


#### - ErrorChar

The parity error replacement character. Bytes received with parity errors are replaced by this character.


#### - BreakChar

The break character. Receipt of this character indicates that a break (temporary pause) occurred in the input stream.


#### - EventChar

The event character. Receipt of this character signals a serial communication event if the SERIAL_EV_RXFLAG flag bit is set in the current wait mask. The wait mask is set by the <a href="..\ntddser\ni-ntddser-ioctl_serial_set_wait_mask.md">IOCTL_SERIAL_SET_WAIT_MASK</a> request. The <a href="..\ntddser\ni-ntddser-ioctl_serial_wait_on_mask.md">IOCTL_SERIAL_WAIT_ON_MASK</a> request initiates a wait for the events in the wait mask.


#### - XonChar

The XON (transmit on) character to use for both transmit and receive operations. The XON and XOFF characters are used for software flow control.


#### - XoffChar

The XOFF (transmit off) character to use for both transmit and receive operations.


## -remarks


This structure is used by the <a href="..\ntddser\ni-ntddser-ioctl_serial_set_chars.md">IOCTL_SERIAL_SET_CHARS</a> and <a href="..\ntddser\ni-ntddser-ioctl_serial_get_chars.md">IOCTL_SERIAL_GET_CHARS</a> requests.

An <b>IOCTL_SERIAL_SET_CHARS</b> request to set the XON and XOFF characters to the same value will fail.



## -see-also

<a href="..\ntddser\ni-ntddser-ioctl_serial_get_chars.md">IOCTL_SERIAL_GET_CHARS</a>

<a href="..\ntddser\ni-ntddser-ioctl_serial_wait_on_mask.md">IOCTL_SERIAL_WAIT_ON_MASK</a>

<a href="..\ntddser\ni-ntddser-ioctl_serial_set_wait_mask.md">IOCTL_SERIAL_SET_WAIT_MASK</a>

<a href="..\ntddser\ni-ntddser-ioctl_serial_set_chars.md">IOCTL_SERIAL_SET_CHARS</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [serports\serports]:%20SERIAL_CHARS structure%20 RELEASE:%20(12/14/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

