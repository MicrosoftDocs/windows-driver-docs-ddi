---
UID: NS:ntddser._SERIAL_TIMEOUTS
title: "_SERIAL_TIMEOUTS"
author: windows-driver-content
description: The SERIAL_TIMEOUTS structure specifies the time-out parameters for read and write operations by the serial port.
old-location: serports\serial_timeouts.htm
old-project: serports
ms.assetid: 58DABEF8-5886-4575-BFB0-C10709BBACAE
ms.author: windowsdriverdev
ms.date: 2/15/2018
ms.keywords: "*PSERIAL_TIMEOUTS, PSERIAL_TIMEOUTS, PSERIAL_TIMEOUTS structure pointer [Serial Ports], SERIAL_TIMEOUTS, SERIAL_TIMEOUTS structure [Serial Ports], _SERIAL_TIMEOUTS, ntddser/PSERIAL_TIMEOUTS, ntddser/SERIAL_TIMEOUTS, serports.serial_timeouts"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	Ntddser.h
apiname:
-	SERIAL_TIMEOUTS
product: Windows
targetos: Windows
req.typenames: SERIAL_TIMEOUTS, *PSERIAL_TIMEOUTS
---

# _SERIAL_TIMEOUTS structure


## -description


The <b>SERIAL_TIMEOUTS</b> structure specifies the time-out parameters for read and write operations by the serial port.


## -syntax


````
typedef struct _SERIAL_TIMEOUTS {
  ULONG ReadIntervalTimeout;
  ULONG ReadTotalTimeoutMultiplier;
  ULONG ReadTotalTimeoutConstant;
  ULONG WriteTotalTimeoutMultiplier;
  ULONG WriteTotalTimeoutConstant;
} SERIAL_TIMEOUTS, *PSERIAL_TIMEOUTS;
````


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



The <b>SERIAL_TIMEOUTS</b> structure is used by the <a href="..\ntddser\ni-ntddser-ioctl_serial_set_timeouts.md">IOCTL_SERIAL_SET_TIMEOUTS</a> and <a href="..\ntddser\ni-ntddser-ioctl_serial_get_timeouts.md">IOCTL_SERIAL_GET_TIMEOUTS</a> I/O control requests. An <b>IOCTL_SERIAL_SET_TIMEOUTS</b> I/O control request uses this structure to specify a set of time-out parameters for the serial port to use for read and write operations. An <b>IOCTL_SERIAL_GET_TIMEOUTS</b> I/O control request uses this structure to retrieve the time-out parameters that were set by the previous <b>IOCTL_SERIAL_SET_TIMEOUTS</b> request.

A read or write request successfully completes when either the specified number of bytes is transferred or the requested read or write operation times out. The request returns the STATUS_SUCCESS status code to indicate that the specified number of bytes was transferred. The request returns the STATUS_TIMEOUT status code to indicate that the operation timed out.

If an <a href="https://msdn.microsoft.com/library/windows/hardware/ff549327">IRP_MJ_READ</a> request specifies a read operation that is Nₜₒₜₐₗ bytes in length, the maximum amount of time, Tₘₐₓ, that the serial port allows for the operation to complete is calculated as follows:

Tₘₐₓ = Nₜₒₜₐₗ * <b>ReadTotalTimeoutMultiplier</b> + <b>ReadTotalTimeoutConstant</b>

A read request that exceeds this maximum completes when the time-out occurs, and returns the STATUS_TIMEOUT status code. The <b>Information</b> field of the I/O status block indicates the number of bytes successfully read before the time-out occurred.

If an <a href="https://msdn.microsoft.com/library/windows/hardware/ff550819">IRP_MJ_WRITE</a> request specifies a write operation that is Nₜₒₜₐₗ bytes in length, the maximum amount of time, Tₘₐₓ, that the serial port allows for the operation to complete is calculated as follows:

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

The <b>SERIAL_TIMEOUTS</b> structure is similar to the <a href="https://msdn.microsoft.com/259aa110-b2c3-4583-a3f9-805a42025a81">COMMTIMEOUTS</a> structure, which is used by the user-mode <a href="https://msdn.microsoft.com/71aa6ab3-d56c-43bc-9932-5b4e61fc4b30">SetCommTimeouts</a> and <a href="https://msdn.microsoft.com/a5375b2e-0992-4e47-a20f-8a793addeef6">GetCommTimeouts</a> functions.

For more information, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff547486">Setting Read and Write Timeouts for a Serial Device</a>.




## -see-also

<a href="https://msdn.microsoft.com/71aa6ab3-d56c-43bc-9932-5b4e61fc4b30">SetCommTimeouts</a>



<a href="..\ntddser\ni-ntddser-ioctl_serial_set_timeouts.md">IOCTL_SERIAL_SET_TIMEOUTS</a>



<a href="..\sercx\nf-sercx-sercxgetreadintervaltimeout.md">SerCxGetReadIntervalTimeout</a>



<a href="https://msdn.microsoft.com/a5375b2e-0992-4e47-a20f-8a793addeef6">GetCommTimeouts</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff550819">IRP_MJ_WRITE</a>



<a href="https://msdn.microsoft.com/259aa110-b2c3-4583-a3f9-805a42025a81">COMMTIMEOUTS</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff549327">IRP_MJ_READ</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [serports\serports]:%20SERIAL_TIMEOUTS structure%20 RELEASE:%20(2/15/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

