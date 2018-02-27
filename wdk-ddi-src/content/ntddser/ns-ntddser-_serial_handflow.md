---
UID: NS:ntddser._SERIAL_HANDFLOW
title: "_SERIAL_HANDFLOW"
author: windows-driver-content
description: The SERIAL_HANDFLOW structure specifies the handshake and flow control settings for a serial port.
old-location: serports\serial_handflow.htm
old-project: serports
ms.assetid: E13148B7-8FCE-4407-80F6-286F0EF65B5C
ms.author: windowsdriverdev
ms.date: 2/15/2018
ms.keywords: "*PSERIAL_HANDFLOW, PSERIAL_HANDFLOW, PSERIAL_HANDFLOW structure pointer [Serial Ports], SERIAL_HANDFLOW, SERIAL_HANDFLOW structure [Serial Ports], _SERIAL_HANDFLOW, ntddser/PSERIAL_HANDFLOW, ntddser/SERIAL_HANDFLOW, serports.serial_handflow"
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	Ntddser.h
api_name:
-	SERIAL_HANDFLOW
product: Windows
targetos: Windows
req.typenames: SERIAL_HANDFLOW, *PSERIAL_HANDFLOW
---

# _SERIAL_HANDFLOW structure


## -description


The <b>SERIAL_HANDFLOW</b> structure specifies the handshake and flow control settings for a serial port.


## -syntax


````
typedef struct _SERIAL_HANDFLOW {
  ULONG ControlHandShake;
  ULONG FlowReplace;
  LONG  XonLimit;
  LONG  XoffLimit;
} SERIAL_HANDFLOW, *PSERIAL_HANDFLOW;
````


## -struct-fields




### -field ControlHandShake

A bitmask that specifies the control lines that the serial port uses for flow control. This member is set to zero or to the bitwise-OR or one or more of the following flags.

<table>
<tr>
<th>Value</th>
<th>Description</th>
</tr>
<tr>
<td>SERIAL_DTR_CONTROL</td>
<td>DTR (data terminal ready) is enabled.</td>
</tr>
<tr>
<td>SERIAL_DTR_HANDSHAKE</td>
<td>DTR is used for input flow control.</td>
</tr>
<tr>
<td>SERIAL_CTS_HANDSHAKE</td>
<td>CTS (clear to send) is used for output flow control.</td>
</tr>
<tr>
<td>SERIAL_DSR_HANDSHAKE</td>
<td>DSR (data set ready) is used for output flow control.</td>
</tr>
<tr>
<td>SERIAL_DCD_HANDSHAKE</td>
<td>DCD (data carrier detect) is used for output flow control.</td>
</tr>
<tr>
<td>SERIAL_DSR_SENSITIVITY</td>
<td>Ignore characters arriving at the serial port when the DSR line is inactive.</td>
</tr>
<tr>
<td>SERIAL_ERROR_ABORT</td>
<td>Abort a transmit or receive operation if an error occurs.</td>
</tr>
</table>
 

SerCx2 supports the SERIAL_CTS_HANDSHAKE flag, and may or may not support the other six flags defined for this member, depending on the serial controller driver and the capabilities of the serial controller hardware. SerCx supports only the first four flags in the preceding table. Serial.sys supports all of the flags in the preceding table.


### -field FlowReplace

A bitmask that specifies flow control behavior. This member is set to zero or to the bitwise-OR or one or more of the following flags.

<table>
<tr>
<th>Value</th>
<th>Description</th>
</tr>
<tr>
<td>SERIAL_AUTO_TRANSMIT</td>
<td>Use XON/XOFF for flow control of transmitted data.
        </td>
</tr>
<tr>
<td>SERIAL_AUTO_RECEIVE</td>
<td>Use XON/XOFF for flow control of received data.</td>
</tr>
<tr>
<td>SERIAL_ERROR_CHAR</td>
<td>Insert the error character into the received data when an error occurs. For more information, see the description of the <b>ErrorChar</b> member in <a href="..\ntddser\ns-ntddser-_serial_chars.md">SERIAL_CHARS</a>.</td>
</tr>
<tr>
<td>SERIAL_NULL_STRIPPING</td>
<td>Automatically strip null characters from received data.</td>
</tr>
<tr>
<td>SERIAL_BREAK_CHAR</td>
<td>Insert the break character into the received data when a break occurs. For more information, see the description of the <b>BreakChar</b> member in <a href="..\ntddser\ns-ntddser-_serial_chars.md">SERIAL_CHARS</a>.</td>
</tr>
<tr>
<td>SERIAL_RTS_CONTROL</td>
<td>RTS (request to send) is enabled.
        </td>
</tr>
<tr>
<td>SERIAL_RTS_HANDSHAKE</td>
<td>RTS is used for output flow control.
        </td>
</tr>
<tr>
<td>SERIAL_XOFF_CONTINUE</td>
<td>Continue to transmit after sending XOFF to the device on the other end of the line.
        </td>
</tr>
</table>
 

SerCx2 supports the SERIAL_RTS_CONTROL and SERIAL_RTS_HANDSHAKE flags, but typically does not support the other six flags defined for this member, depending on the serial controller driver and the capabilities of the serial controller hardware. SerCx supports only the SERIAL_RTS_CONTROL and SERIAL_RTS_HANDSHAKE flags. Serial.sys supports all of the flags in the preceding table.


### -field XonLimit

XON limit. When the number of characters in the internal receive buffer falls below the XON limit, the serial controller driver uses the flow control signals to tell the sender to resume sending characters.


### -field XoffLimit

XOFF limit. When the number of characters in the internal receive buffer reaches the XOFF limit, the serial controller driver uses the flow control signals to tell the sender to stop sending characters.


## -remarks



This structure is used by the <a href="..\ntddser\ni-ntddser-ioctl_serial_get_handflow.md">IOCTL_SERIAL_GET_HANDFLOW</a> and <a href="..\ntddser\ni-ntddser-ioctl_serial_set_handflow.md">IOCTL_SERIAL_SET_HANDFLOW</a> requests.

After sending an XOFF (transmit off) character, the serial port stops transmitting immediately, without sending any more characters. This behavior supports serial ports that interpret any character that follows an XOFF as an implied XON (transmit on).

SerCx2 and SerCx support only subsets of the flags that are defined for the <b>ControlHandShake</b> and <b>FlowControl</b> members. An <b>IOCTL_SERIAL_SET_HANDFLOW</b> request that specifies an unsupported flag is completed with STATUS_NOT_IMPLEMENTED.




## -see-also

<a href="..\ntddser\ni-ntddser-ioctl_serial_get_handflow.md">IOCTL_SERIAL_GET_HANDFLOW</a>



<a href="..\ntddser\ni-ntddser-ioctl_serial_set_handflow.md">IOCTL_SERIAL_SET_HANDFLOW</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [serports\serports]:%20SERIAL_HANDFLOW structure%20 RELEASE:%20(2/15/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

