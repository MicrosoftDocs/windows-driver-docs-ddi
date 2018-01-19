---
UID: NI:ntddser.IOCTL_SERIAL_GET_WAIT_MASK
title: IOCTL_SERIAL_GET_WAIT_MASK
author: windows-driver-content
description: The IOCTL_SERIAL_GET_WAIT_MASK request returns the event wait mask that is currently set for the serial controller.
old-location: serports\ioctl_serial_get_wait_mask.htm
old-project: serports
ms.assetid: 2ee8591a-f48e-43ad-8b88-74a1401aad07
ms.author: windowsdriverdev
ms.date: 12/14/2017
ms.keywords: SdBusSubmitRequestAsync
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: ioctl
req.header: ntddser.h
req.include-header: Ntddser.h
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: IOCTL_SERIAL_GET_WAIT_MASK
req.alt-loc: Ntddser.h
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
req.typenames: SD_REQUEST_FUNCTION
---

# IOCTL_SERIAL_GET_WAIT_MASK IOCTL



## -description
The <b>IOCTL_SERIAL_GET_WAIT_MASK</b> request returns the event wait mask that is currently set for the serial controller.

A client can wait for the wait events represented by flag bits <b>SERIAL_EV_RXCHAR</b> through <b>SERIAL_EV_EVENT2</b>. For more information about these event flags, see the Remarks section.

To set an event wait mask, a client can use an <a href="..\ntddser\ni-ntddser-ioctl_serial_set_wait_mask.md">IOCTL_SERIAL_SET_WAIT_MASK</a> request. To wait for the occurrence of a wait event, a client uses an <a href="..\ntddser\ni-ntddser-ioctl_serial_wait_on_mask.md">IOCTL_SERIAL_WAIT_ON_MASK</a> request.



## -ioctlparameters

### -input-buffer
None.


### -input-buffer-length
None.


### -output-buffer
The <b>AssociatedIrp.SystemBuffer</b> member points to a client-allocated ULONG buffer that the serial controller driver uses to output the wait mask. The wait mask is either zero or the bitwise-OR of one or more of the <b>SERIAL_EV_</b><i>XXX</i> event flags.


### -output-buffer-length
The <b>Parameters.DeviceIoControl.OutputBufferLength</b> member is set to the size, in bytes, of a ULONG.


### -in-out-buffer

<text></text>

### -inout-buffer-length

<text></text>

### -status-block
I/O Status block
If the request is successful, the <b>Information</b> member is set to the size, in bytes, of a ULONG. Otherwise, the <b>Information</b> member is set to zero.

The <b>Status</b> member is set to one of the <a href="serial_device_control_requests.htm#generic_status_values_for_serial_device_control_requests">Generic Status Values for Serial Device Control Requests</a>.


## -remarks

    The <b>SERIAL_EV_</b><i>XXX</i> constants define the flag bits in the wait mask for a serial port.
   


<pre class="syntax">#define SERIAL_EV_RXCHAR     0x0001
#define SERIAL_EV_RXFLAG     0x0002
#define SERIAL_EV_TXEMPTY    0x0004
#define SERIAL_EV_CTS        0x0008
#define SERIAL_EV_DSR        0x0010
#define SERIAL_EV_RLSD       0x0020
#define SERIAL_EV_BREAK      0x0040
#define SERIAL_EV_ERR        0x0080
#define SERIAL_EV_RING       0x0100
#define SERIAL_EV_PERR       0x0200
#define SERIAL_EV_RX80FULL   0x0400
#define SERIAL_EV_EVENT1     0x0800
#define SERIAL_EV_EVENT2     0x1000</pre>




A character was received and placed in the input buffer.

The event character was received and placed in the input buffer. The event character value is set by the <a href="..\ntddser\ni-ntddser-ioctl_serial_set_chars.md">IOCTL_SERIAL_SET_CHARS</a> request.

The last character was transmitted from the output buffer, which is now empty.

The CTS (clear to send) signal changed state.

The DSR (data set ready) signal changed state.

The RLSD (receive line signal detect) signal changed state.

A break was detected in the input stream.

A line status error occurred. Possible line status errors are SERIAL_ERROR_FRAMING, SERIAL_ERROR_OVERRUN, and SERIAL_ERROR_PARITY. For more information about these errors, see the description of the <b>Errors</b> member in <a href="..\ntddser\ns-ntddser-_serial_status.md">SERIAL_STATUS</a>.

A ring signal was detected.

A printer error occurred.

The receive buffer is 80 percent full.

Provider-specific event number 1 occurred.

Provider-specific event number 2 occurred.

The <b>SERIAL_EV_</b><i>XXX</i> constants define the types of events that can be specified in a wait mask. After a client (application or peripheral driver) opens a connection to a serial port, the client can specify a wait mask that indicates the types of events that the client needs to monitor. These events are changes in the hardware state of the serial port. When an event in the wait mask occurs, the client is notified.

The <a href="..\ntddser\ni-ntddser-ioctl_serial_set_wait_mask.md">IOCTL_SERIAL_SET_WAIT_MASK</a> and <b>IOCTL_SERIAL_GET_WAIT_MASK</b> control requests use event wait masks to specify a set of events on which a client can wait. A wait mask value is either zero or the bitwise-OR of one or more <b>SERIAL_EV_</b><i>XXX</i> constants. A wait mask value of zero indicates that the client is not waiting for any events.

The client sends an <a href="..\ntddser\ni-ntddser-ioctl_serial_wait_on_mask.md">IOCTL_SERIAL_WAIT_ON_MASK</a> control request to wait for an event in the currently set wait mask. The serial controller driver completes this request when an event in the wait mask occurs.

The following table shows which <b>SERIAL_EV_</b><i>XXX</i> flag bits are supported by SerCx2, SerCx, and Serial.sys. A <b>Yes</b> entry in the table indicates that the serial framework extension or driver supports the corresponding flag bit. A <b>No</b> entry indicates that the flag bit is <u>not</u> supported.

For more information about SerCx2, SerCx, and Serial.sys, see <a href="https://msdn.microsoft.com/1EA0221E-0F68-429B-9DA5-4AE2D3394A09">Serial Controller Drivers Overview</a>.


## -see-also
<dl>
<dt>
<a href="..\ntddser\ni-ntddser-ioctl_serial_get_chars.md">IOCTL_SERIAL_GET_CHARS</a>
</dt>
<dt>
<a href="..\ntddser\ni-ntddser-ioctl_serial_set_chars.md">IOCTL_SERIAL_SET_CHARS</a>
</dt>
<dt>
<a href="..\ntddser\ni-ntddser-ioctl_serial_set_wait_mask.md">IOCTL_SERIAL_SET_WAIT_MASK</a>
</dt>
<dt>
<a href="..\ntddser\ni-ntddser-ioctl_serial_wait_on_mask.md">IOCTL_SERIAL_WAIT_ON_MASK</a>
</dt>
<dt>
<a href="..\ntddser\ns-ntddser-_serial_chars.md">SERIAL_CHARS</a>
</dt>
<dt>
<a href="..\ntddser\ns-ntddser-_serial_status.md">SERIAL_STATUS</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [serports\serports]:%20IOCTL_SERIAL_GET_WAIT_MASK control code%20 RELEASE:%20(12/14/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

