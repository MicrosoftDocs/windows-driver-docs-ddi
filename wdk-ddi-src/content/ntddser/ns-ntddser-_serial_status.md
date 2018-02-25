---
UID: NS:ntddser._SERIAL_STATUS
title: "_SERIAL_STATUS"
author: windows-driver-content
description: The SERIAL_STATUS structure contains status information about the serial port.
old-location: serports\serial_status.htm
old-project: serports
ms.assetid: F77EF32F-FAB6-4800-9241-5AAA9885DEF5
ms.author: windowsdriverdev
ms.date: 2/15/2018
ms.keywords: ",  , *, *PSERIAL_STATUS, ,, A, E, I, L, P, PSERIAL_STATUS, PSERIAL_STATUS structure pointer [Serial Ports], R, S, SERIAL_STATUS, SERIAL_STATUS structure [Serial Ports], T, U, _, _SERIAL_STATUS, ntddser/PSERIAL_STATUS, ntddser/SERIAL_STATUS, serports.serial_status"
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
-	SERIAL_STATUS
product: Windows
targetos: Windows
req.typenames: SERIAL_STATUS, *PSERIAL_STATUS
---

# _SERIAL_STATUS structure


## -description


The <b>SERIAL_STATUS</b> structure contains status information about the serial port.


## -syntax


````
typedef struct _SERIAL_STATUS {
  ULONG   Errors;
  ULONG   HoldReasons;
  ULONG   AmountInInQueue;
  ULONG   AmountInOutQueue;
  BOOLEAN EofReceived;
  BOOLEAN WaitForImmediate;
} SERIAL_STATUS, *PSERIAL_STATUS;
````


## -struct-fields




### -field Errors

A set of flags to indicate the receive errors that have occurred in the input stream. This member is set to zero or to the bitwise-OR of one or more of the following flag bits.

<table>
<tr>
<th>Flag name</th>
<th>Meaning</th>
</tr>
<tr>
<td>SERIAL_ERROR_QUEUEOVERRUN</td>
<td>The serial controller driver's internal input buffer was overrun by data received from the input stream. Either the input buffer is full, or a character was received after the EOF (end of file) character.</td>
</tr>
<tr>
<td>SERIAL_ERROR_OVERRUN</td>
<td>The hardware receive FIFO was overrun by data received from the input stream.</td>
</tr>
<tr>
<td>SERIAL_ERROR_BREAK</td>
<td>A break condition occurred on the input line.</td>
</tr>
<tr>
<td>SERIAL_ERROR_PARITY</td>
<td>A parity error was detected in a byte received from the input stream.</td>
</tr>
<tr>
<td>SERIAL_ERROR_FRAMING</td>
<td>A framing error was detected in the bytes received from the input stream.</td>
</tr>
</table>
 

After the serial controller driver supplies the accumulated SERIAL_ERROR_<i>XXX</i> flags to satisfy an <a href="..\ntddser\ni-ntddser-ioctl_serial_get_commstatus.md">IOCTL_SERIAL_GET_COMMSTATUS</a> request, the driver resets the flags to zero.


### -field HoldReasons

A set of flags to indicate the reasons that the serial port is currently waiting to transmit bytes to the output stream. This member is set to zero or to the bitwise-OR of one or more of the following flag bits.

<table>
<tr>
<th>Flag name</th>
<th>Meaning</th>
</tr>
<tr>
<td>SERIAL_TX_WAITING_FOR_CTS</td>
<td>Waiting for the CTS (clear to send) signal.</td>
</tr>
<tr>
<td>SERIAL_TX_WAITING_FOR_DSR</td>
<td>Waiting for the DSR (data set ready) signal.</td>
</tr>
<tr>
<td>SERIAL_TX_WAITING_FOR_DCD</td>
<td>Waiting for the DCD (data carrier detect) signal.</td>
</tr>
<tr>
<td>SERIAL_TX_WAITING_FOR_XON</td>
<td>Waiting for the XON (transmit on) signal.</td>
</tr>
<tr>
<td>SERIAL_TX_WAITING_ON_BREAK</td>
<td>Sending a break (spacing value) signal.</td>
</tr>
<tr>
<td>SERIAL_TX_WAITING_XOFF_SENT</td>
<td>Sent an XOFF (transmit off) signal. This signal marks the end of transmission from the serial port, which then waits for the device on the other end of the line to start transmitting. The other device receives the transmitted XOFF signal as an XON signal.</td>
</tr>
</table>
 

<b>HoldReasons</b> is zero if the serial port has no reason to stop transmitting bytes.


### -field AmountInInQueue

The number of bytes of data received from the serial port that are currently available to be read from the input buffer.


### -field AmountInOutQueue

The number of bytes of transmit data that are currently waiting to be written from the output buffer to the serial port.


### -field EofReceived

Whether an EOF (end of file) character has been received. This member is <b>TRUE</b> if an EOF has been received. Otherwise, it is <b>FALSE</b>. The EOF character marks the end of the input stream.


### -field WaitForImmediate

Whether the serial port is waiting to transmit an immediate character. This member is <b>TRUE</b> if the serial port is waiting to transmit an immediate character. Otherwise, it is <b>FALSE</b>. Transmission of an immediate character might be delayed if any flag bit other than SERIAL_TX_WAITING_FOR_XON is set in the <b>HoldReasons</b> member. For more information about immediate characters, see <a href="..\ntddser\ni-ntddser-ioctl_serial_immediate_char.md">IOCTL_SERIAL_IMMEDIATE_CHAR</a>.


## -remarks



This structure is used by the <a href="..\ntddser\ni-ntddser-ioctl_serial_get_commstatus.md">IOCTL_SERIAL_GET_COMMSTATUS</a> request.




## -see-also

<a href="..\ntddser\ni-ntddser-ioctl_serial_immediate_char.md">IOCTL_SERIAL_IMMEDIATE_CHAR</a>



<a href="..\ntddser\ni-ntddser-ioctl_serial_get_commstatus.md">IOCTL_SERIAL_GET_COMMSTATUS</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [serports\serports]:%20SERIAL_STATUS structure%20 RELEASE:%20(2/15/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

