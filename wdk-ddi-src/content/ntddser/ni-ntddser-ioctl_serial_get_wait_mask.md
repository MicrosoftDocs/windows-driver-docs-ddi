---
UID: NI:ntddser.IOCTL_SERIAL_GET_WAIT_MASK
title: IOCTL_SERIAL_GET_WAIT_MASK (ntddser.h)
description: The IOCTL_SERIAL_GET_WAIT_MASK request returns the event wait mask that is currently set for the serial controller.
old-location: serports\ioctl_serial_get_wait_mask.htm
tech.root: serports
ms.assetid: 2ee8591a-f48e-43ad-8b88-74a1401aad07
ms.date: 04/23/2018
keywords: ["IOCTL_SERIAL_GET_WAIT_MASK IOCTL"]
ms.keywords: IOCTL_SERIAL_GET_WAIT_MASK, IOCTL_SERIAL_GET_WAIT_MASK control, IOCTL_SERIAL_GET_WAIT_MASK control code [Serial Ports], ntddser/IOCTL_SERIAL_GET_WAIT_MASK, serports.ioctl_serial_get_wait_mask, serref_d06a9ed8-0871-455b-8d91-8f530adfcfe9.xml
req.header: ntddser.h
req.include-header: Ntddser.h
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
targetos: Windows
req.typenames: 
f1_keywords:
 - IOCTL_SERIAL_GET_WAIT_MASK
 - ntddser/IOCTL_SERIAL_GET_WAIT_MASK
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - Ntddser.h
api_name:
 - IOCTL_SERIAL_GET_WAIT_MASK
---

# IOCTL_SERIAL_GET_WAIT_MASK IOCTL


## -description

The <b>IOCTL_SERIAL_GET_WAIT_MASK</b> request returns the event wait mask that is currently set for the serial controller.

A client can wait for the wait events represented by flag bits <b>SERIAL_EV_RXCHAR</b> through <b>SERIAL_EV_EVENT2</b>. For more information about these event flags, see the Remarks section.

To set an event wait mask, a client can use an <a href="/windows-hardware/drivers/ddi/ntddser/ni-ntddser-ioctl_serial_set_wait_mask">IOCTL_SERIAL_SET_WAIT_MASK</a> request. To wait for the occurrence of a wait event, a client uses an <a href="/windows-hardware/drivers/ddi/ntddser/ni-ntddser-ioctl_serial_wait_on_mask">IOCTL_SERIAL_WAIT_ON_MASK</a> request.

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

### -inout-buffer-length

### -status-block

If the request is successful, the <b>Information</b> member is set to the size, in bytes, of a ULONG. Otherwise, the <b>Information</b> member is set to zero.

The <b>Status</b> member is set to one of the <a href="/windows-hardware/drivers/serports/serial-device-control-requests2">Generic Status Values for Serial Device Control Requests</a>.

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




The <b>SERIAL_EV_</b><i>XXX</i> constants define the types of events that can be specified in a wait mask. After a client (application or peripheral driver) opens a connection to a serial port, the client can specify a wait mask that indicates the types of events that the client needs to monitor. These events are changes in the hardware state of the serial port. When an event in the wait mask occurs, the client is notified.

The <a href="/windows-hardware/drivers/ddi/ntddser/ni-ntddser-ioctl_serial_set_wait_mask">IOCTL_SERIAL_SET_WAIT_MASK</a> and <b>IOCTL_SERIAL_GET_WAIT_MASK</b> control requests use event wait masks to specify a set of events on which a client can wait. A wait mask value is either zero or the bitwise-OR of one or more <b>SERIAL_EV_</b><i>XXX</i> constants. A wait mask value of zero indicates that the client is not waiting for any events.

The client sends an <a href="/windows-hardware/drivers/ddi/ntddser/ni-ntddser-ioctl_serial_wait_on_mask">IOCTL_SERIAL_WAIT_ON_MASK</a> control request to wait for an event in the currently set wait mask. The serial controller driver completes this request when an event in the wait mask occurs.

The following table shows which <b>SERIAL_EV_</b><i>XXX</i> flag bits are supported by SerCx2, SerCx, and Serial.sys. A <b>Yes</b> entry in the table indicates that the serial framework extension or driver supports the corresponding flag bit. A <b>No</b> entry indicates that the flag bit is <u>not</u> supported.

<table>
<tr>
<th>Flag bit</th>
<th>SerCx2</th>
<th>SerCx</th>
<th>Serial.sys</th>
</tr>
<tr>
<td><b>SERIAL_EV_RXCHAR</b></td>
<td>Yes</td>
<td>Yes</td>
<td>Yes</td>
</tr>
<tr>
<td><b>SERIAL_EV_RXFLAG</b></td>
<td>See note.</td>
<td>No</td>
<td>Yes</td>
</tr>
<tr>
<td><b>SERIAL_EV_TXEMPTY</b></td>
<td>Yes</td>
<td>Yes</td>
<td>Yes</td>
</tr>
<tr>
<td><b>SERIAL_EV_CTS</b></td>
<td>Yes</td>
<td>Yes</td>
<td>Yes</td>
</tr>
<tr>
<td><b>SERIAL_EV_DSR</b></td>
<td>Yes</td>
<td>Yes</td>
<td>Yes</td>
</tr>
<tr>
<td><b>SERIAL_EV_RLSD</b></td>
<td>See note.</td>
<td>Yes</td>
<td>Yes</td>
</tr>
<tr>
<td><b>SERIAL_EV_BREAK</b></td>
<td>Yes</td>
<td>Yes</td>
<td>Yes</td>
</tr>
<tr>
<td><b>SERIAL_EV_ERR</b></td>
<td>Yes</td>
<td>Yes</td>
<td>Yes</td>
</tr>
<tr>
<td><b>SERIAL_EV_RING</b></td>
<td>See note.</td>
<td>Yes</td>
<td>Yes</td>
</tr>
<tr>
<td><b>SERIAL_EV_PERR</b></td>
<td>See note.</td>
<td>No</td>
<td>No</td>
</tr>
<tr>
<td><b>SERIAL_EV_RX80FULL</b></td>
<td>See note.</td>
<td>No</td>
<td>Yes</td>
</tr>
<tr>
<td><b>SERIAL_EV_EVENT1</b></td>
<td>See note.</td>
<td>No</td>
<td>No</td>
</tr>
<tr>
<td><b>SERIAL_EV_EVENT2</b></td>
<td>See note.</td>
<td>No</td>
<td>No</td>
</tr>
</table>
 

<div class="alert"><b>Note</b>  SerCx2 may or may not support the flag bit in the indicated table entry, depending on the serial controller driver and the capabilities of the serial controller hardware.</div>
<div> </div>
For more information about SerCx2, SerCx, and Serial.sys, see <a href="/previous-versions/jj241971(v=vs.85)">Serial Controller Drivers Overview</a>.

## -see-also

<a href="/windows-hardware/drivers/ddi/ntddser/ni-ntddser-ioctl_serial_get_chars">IOCTL_SERIAL_GET_CHARS</a>



<a href="/windows-hardware/drivers/ddi/ntddser/ni-ntddser-ioctl_serial_set_chars">IOCTL_SERIAL_SET_CHARS</a>



<a href="/windows-hardware/drivers/ddi/ntddser/ni-ntddser-ioctl_serial_set_wait_mask">IOCTL_SERIAL_SET_WAIT_MASK</a>



<a href="/windows-hardware/drivers/ddi/ntddser/ni-ntddser-ioctl_serial_wait_on_mask">IOCTL_SERIAL_WAIT_ON_MASK</a>



<a href="/windows-hardware/drivers/ddi/ntddser/ns-ntddser-_serial_chars">SERIAL_CHARS</a>



<a href="/windows-hardware/drivers/ddi/ntddser/ns-ntddser-_serial_status">SERIAL_STATUS</a>