---
UID: NS:ntddser._SERIAL_TIMEOUTS
title: _SERIAL_TIMEOUTS (ntddser.h)
description: The SERIAL_TIMEOUTS structure specifies the time-out parameters for read and write operations by the serial port.
old-location: serports\serial_timeouts.htm
tech.root: serports
ms.assetid: 58DABEF8-5886-4575-BFB0-C10709BBACAE
ms.date: 04/23/2018
keywords: ["SERIAL_TIMEOUTS structure"]
ms.keywords: "*PSERIAL_TIMEOUTS, PSERIAL_TIMEOUTS, PSERIAL_TIMEOUTS structure pointer [Serial Ports], SERIAL_TIMEOUTS, SERIAL_TIMEOUTS structure [Serial Ports], _SERIAL_TIMEOUTS, ntddser/PSERIAL_TIMEOUTS, ntddser/SERIAL_TIMEOUTS, serports.serial_timeouts"
req.header: ntddser.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: Supported starting with Windows 2000.
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
req.typenames: SERIAL_TIMEOUTS, *PSERIAL_TIMEOUTS
f1_keywords:
 - _SERIAL_TIMEOUTS
 - ntddser/_SERIAL_TIMEOUTS
 - PSERIAL_TIMEOUTS
 - ntddser/PSERIAL_TIMEOUTS
 - SERIAL_TIMEOUTS
 - ntddser/SERIAL_TIMEOUTS
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - Ntddser.h
api_name:
 - SERIAL_TIMEOUTS
---

# _SERIAL_TIMEOUTS structure


## -description

The <b>SERIAL_TIMEOUTS</b> structure specifies the time-out parameters for read and write operations by the serial port.

## -struct-fields

### -field ReadIntervalTimeout

The maximum amount of time, in milliseconds, that is allowed between two consecutive bytes in a read operation. A read operation that exceeds this maximum times out. This maximum does not apply to the time interval that precedes the reading of the first byte. A value of zero indicates that interval time-outs are not used. For more information, see Remarks.

### -field ReadTotalTimeoutMultiplier

The maximum amount of time, in milliseconds, that is allowed per byte in a read operation. A read operation that exceeds this maximum times out. For more information, see Remarks.

### -field ReadTotalTimeoutConstant

The maximum amount of additional time, in milliseconds, that is allowed per read operation. A read operation that exceeds this maximum times out. For more information, see Remarks.

### -field WriteTotalTimeoutMultiplier

The maximum total time, in milliseconds, that is allowed per byte in a write operation. A write operation that exceeds this maximum times out. For more information, see Remarks.

### -field WriteTotalTimeoutConstant

The maximum amount of additional time, in milliseconds, that is allowed per write operation. A write operation that exceeds this maximum times out. For more information, see Remarks.

## -remarks

The <b>SERIAL_TIMEOUTS</b> structure is used by the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddser/ni-ntddser-ioctl_serial_set_timeouts">IOCTL_SERIAL_SET_TIMEOUTS</a> and <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddser/ni-ntddser-ioctl_serial_get_timeouts">IOCTL_SERIAL_GET_TIMEOUTS</a> I/O control requests. An <b>IOCTL_SERIAL_SET_TIMEOUTS</b> I/O control request uses this structure to specify a set of time-out parameters for the serial port to use for read and write operations. An <b>IOCTL_SERIAL_GET_TIMEOUTS</b> I/O control request uses this structure to retrieve the time-out parameters that were set by the previous <b>IOCTL_SERIAL_SET_TIMEOUTS</b> request.

A read or write request successfully completes when either the specified number of bytes is transferred or the requested read or write operation times out. The request returns the STATUS_SUCCESS status code to indicate that the specified number of bytes was transferred. The request returns the STATUS_TIMEOUT status code to indicate that the operation timed out.

If an <a href="https://docs.microsoft.com/windows-hardware/drivers/ifs/irp-mj-read">IRP_MJ_READ</a> request specifies a read operation that is Nₜₒₜₐₗ bytes in length, the maximum amount of time, Tₘₐₓ, that the serial port allows for the operation to complete is calculated as follows:

Tₘₐₓ = Nₜₒₜₐₗ * <b>ReadTotalTimeoutMultiplier</b> + <b>ReadTotalTimeoutConstant</b>

A read request that exceeds this maximum completes when the time-out occurs, and returns the STATUS_TIMEOUT status code. The <b>Information</b> field of the I/O status block indicates the number of bytes successfully read before the time-out occurred.

If an <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/irp-mj-write">IRP_MJ_WRITE</a> request specifies a write operation that is Nₜₒₜₐₗ bytes in length, the maximum amount of time, Tₘₐₓ, that the serial port allows for the operation to complete is calculated as follows:

Tₘₐₓ = Nₜₒₜₐₗ * <b>WriteTotalTimeoutMultiplier</b> + <b>WriteTotalTimeoutConstant</b>

A write request that exceeds this maximum completes when the time-out occurs, and returns the STATUS_TIMEOUT status code. The <b>Information</b> field of the I/O status block indicates the number of bytes successfully written before the time-out occurred.

The maximum time, Tₘₐₓ, that is allowed for a read or write operation to complete is always measured from when the serial port starts the requested operation, and not from when the client submits the request.

If <b>ReadIntervalTimeout</b>, <b>ReadTotalTimeoutMultiplier</b>, and <b>ReadTotalTimeoutConstant</b> are all zero, read operations never time out. If <b>WriteTotalTimeoutMultiplier</b> and <b>WriteTotalTimeoutConstant</b> are both zero, write operations never time out.

If <b>ReadIntervalTimeout</b> is zero, there is no maximum interval between consecutive bytes in read operations, and time-outs are based solely on the <b>ReadTotalTimeoutMultiplier</b> and <b>ReadTotalTimeoutConstant</b> members.

If both <b>ReadTotalTimeoutMultiplier</b> and <b>ReadTotalTimeoutConstant</b> are zero, and <b>ReadIntervalTimeout</b> is less than MAXULONG and greater than zero, a read operation times out only if the interval between a pair of consecutively received bytes exceeds <b>ReadIntervalTimeout</b>. If these three time-out values are used, and the serial port's input buffer is empty when a read request is sent to the port, this request never times out until after the port receives at least one byte of new data.

If <b>ReadIntervalTimeout</b> is set to MAXULONG, and both <b>ReadTotalTimeoutConstant</b> and <b>ReadTotalTimeoutMultiplier</b> are zero, a read request completes immediately with the bytes that have already been received, even if no bytes have been received. In this case, the read request returns the STATUS_SUCCESS status code.

If both <b>ReadIntervalTimeout</b> and <b>ReadTotalTimeoutMultiplier</b> are set to MAXULONG, and <b>ReadTotalTimeoutConstant</b> is set to a value greater than zero and less than MAXULONG, a read request behaves as follows:

<ul>
<li>
If there are any bytes in the serial port's input buffer, the read request completes immediately with the bytes that are in the buffer and returns the STATUS_SUCCESS status code.

</li>
<li>
If there are no bytes in the input buffer, the serial port waits until a byte arrives, and then immediately completes the read request with the one byte of data and returns the STATUS_SUCCESS status code.

</li>
<li>
If no bytes arrive within the time specified by <b>ReadTotalTimeoutConstant</b>, the read request times out, sets the <b>Information</b> field of the I/O status block to zero,  and returns the STATUS_TIMEOUT status code.

</li>
</ul>
An <b>IOCTL_SERIAL_SET_TIMEOUTS</b> request fails and returns an INVALID_PARAMETER error status code if <b>ReadIntervalTimeout</b> and <b>ReadTotalTimeoutConstant</b> are both set to MAXULONG.

A read-interval time-out can be used to detect the end of an incoming data stream when the length of the data stream is not known in advance. If a read request uses this technique, a STATUS_TIMEOUT completion status code usually means that the request completed successfully.

A read-interval time-out occurs when the interval between incoming bytes exceeds the <b>ReadIntervalTimeout</b> value. Time-out intervals are measured relative to the system clock, and the accuracy of the time-out measurement is limited by the granularity of the system clock. As a result, a time-out can occur between one system clock tick earlier and one tick later than the specified time-out interval, depending on where exactly the start and end times of this interval fall between system clock ticks. Time-outs might occur even later if system clock interrupt processing is delayed by interrupt processing for other devices. If a specified time-out interval is close to or smaller than the period between system clock ticks, the time-out might occur immediately, with no delay.

A possible way to more accurately measure smaller time-out intervals is to decrease the time between system clock ticks, but doing so is likely to increase power consumption. In addition, reducing the system clock period might not reliably achieve a finer system clock granularity unless interrupt-related processing by the various drivers in the platform can be guaranteed not to delay the processing of system clock interrupts.

The <b>SERIAL_TIMEOUTS</b> structure is similar to the <a href="https://docs.microsoft.com/windows/desktop/api/winbase/ns-winbase-_commtimeouts">COMMTIMEOUTS</a> structure, which is used by the user-mode <a href="https://docs.microsoft.com/windows/desktop/api/winbase/nf-winbase-setcommtimeouts">SetCommTimeouts</a> and <a href="https://docs.microsoft.com/windows/desktop/api/winbase/nf-winbase-getcommtimeouts">GetCommTimeouts</a> functions.

For more information, see <a href="https://docs.microsoft.com/previous-versions/ff547486(v=vs.85)">Setting Read and Write Timeouts for a Serial Device</a>.

## -see-also

<a href="https://docs.microsoft.com/windows/desktop/api/winbase/ns-winbase-_commtimeouts">COMMTIMEOUTS</a>



<a href="https://docs.microsoft.com/windows/desktop/api/winbase/nf-winbase-getcommtimeouts">GetCommTimeouts</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddser/ni-ntddser-ioctl_serial_set_timeouts">IOCTL_SERIAL_SET_TIMEOUTS</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ifs/irp-mj-read">IRP_MJ_READ</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/irp-mj-write">IRP_MJ_WRITE</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/sercx/nf-sercx-sercxgetreadintervaltimeout">SerCxGetReadIntervalTimeout</a>



<a href="https://docs.microsoft.com/windows/desktop/api/winbase/nf-winbase-setcommtimeouts">SetCommTimeouts</a>

