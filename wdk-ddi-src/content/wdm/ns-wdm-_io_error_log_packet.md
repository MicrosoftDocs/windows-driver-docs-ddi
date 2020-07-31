---
UID: NS:wdm._IO_ERROR_LOG_PACKET
title: _IO_ERROR_LOG_PACKET (wdm.h)
description: The IO_ERROR_LOG_PACKET structure serves as the header for an error log entry.
old-location: kernel\io_error_log_packet.htm
tech.root: kernel
ms.assetid: 4bf54017-d142-4534-8a5a-c7f267a1554b
ms.date: 04/30/2018
keywords: ["_IO_ERROR_LOG_PACKET structure"]
ms.keywords: "*PIO_ERROR_LOG_PACKET, IO_ERROR_LOG_PACKET, IO_ERROR_LOG_PACKET structure [Kernel-Mode Driver Architecture], PIO_ERROR_LOG_PACKET, PIO_ERROR_LOG_PACKET structure pointer [Kernel-Mode Driver Architecture], _IO_ERROR_LOG_PACKET, kernel.io_error_log_packet, kstruct_b_04c24dbc-a479-437c-adc2-b29294596564.xml, wdm/IO_ERROR_LOG_PACKET, wdm/PIO_ERROR_LOG_PACKET"
f1_keywords:
 - "wdm/IO_ERROR_LOG_PACKET"
 - "IO_ERROR_LOG_PACKET"
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h
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
- Wdm.h
api_name:
- IO_ERROR_LOG_PACKET
targetos: Windows
req.typenames: IO_ERROR_LOG_PACKET, *PIO_ERROR_LOG_PACKET
---

# _IO_ERROR_LOG_PACKET structure


## -description


The <b>IO_ERROR_LOG_PACKET</b> structure serves as the header for an error log entry.


## -struct-fields




### -field MajorFunctionCode

Indicates the <b>IRP_MJ_<i>XXX</i></b> major function code of the IRP the driver was handling when the error occurred. Setting this value is optional.


### -field RetryCount

Indicates the number of times the driver has retried the operation and encountered this error. Use zero to indicate the driver attempted the operation once, or add one for each retry beyond the initial attempt.


### -field DumpDataSize

Indicates the size, in bytes, of the variable-length <b>DumpData</b> member of this structure. The specified value must be a multiple of <b>sizeof</b>(ULONG). 


### -field NumberOfStrings

Indicates the number of insertion strings the driver will supply with this error log entry. Drivers set this value to zero for errors that need no insertion strings. The Event Viewer uses these strings to fill in the "%2" through "%<i>n</i>" entries in the string template for this error code.

The null-terminated Unicode strings themselves follow the <b>IO_ERROR_LOG_PACKET</b> structure in memory.


### -field StringOffset

Indicates the offset, in bytes, from the beginning of the structure, at which any driver-supplied insertion string data begins. Normally this will be <b>sizeof</b>(<b>IO_ERROR_LOG_PACKET</b>) plus the value of the <b>DumpDataSize</b> member. If there are no driver-supplied insertion strings, <b>StringOffset</b> can be zero.


### -field EventCategory

Specifies the event category for the error. A driver specifies the event categories it supports and corresponding descriptive strings in its message catalog. The Event Viewer displays the descriptive string as the <b>Category</b> value for the error.


### -field ErrorCode

Specifies the type of error. The Event Viewer uses the error code to determine which string to display as the Description value for the error. The Event Viewer takes the string template for the error supplied in the driver's message catalog, replaces "%1" in the template with the name of the driver's device object, and replaces "%2" through "%<i>n</i>" with the insertion strings supplied with the error log entry.

<b>ErrorCode</b> is a system-defined or driver-defined constant; see <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/logging-errors">Logging Errors</a> for more information. 


### -field UniqueErrorValue

A driver-specific value that indicates where the error was detected in the driver. Setting this value is optional.


### -field FinalStatus

Specifies the NTSTATUS value to be returned for the operation that triggered the error. Setting this value is optional.


### -field SequenceNumber

Specifies a driver-assigned sequence number for the current IRP, which should be constant for the life of a given request. Setting this value is optional.


### -field IoControlCode

For an <a href="https://docs.microsoft.com/windows-hardware/drivers/ifs/irp-mj-device-control">IRP_MJ_DEVICE_CONTROL</a> or <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/irp-mj-internal-device-control">IRP_MJ_INTERNAL_DEVICE_CONTROL</a> IRP, this member specifies the I/O control code for the request that trigged the error. Otherwise, this value is zero. Setting this value is optional.


### -field DeviceOffset

Specifies the driver-specified offset into the device where the error occurred. Setting this value is optional.


### -field DumpData

A variable-size array that can be used to store driver-specific binary data, such as register values or any other information useful in identifying the cause of the error. Drivers must specify the size, in bytes, of the array in the <b>DumpDataSize</b> member of this structure.


## -remarks



Drivers use the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-ioallocateerrorlogentry">IoAllocateErrorLogEntry</a> routine to allocate an error log entry. The <b>IO_ERROR_LOG_PACKET</b> structure serves as the header for the returned buffer. It is followed in memory by any insertion strings for the log entry.

Note that the I/O manager itself inserts some information into the system error log, such as the name of the device and driver. The I/O manager reserves 80 bytes to hold this information. If the size of this information exceeds 80 bytes, then the I/O manager truncates the driver's insertion strings as necessary.

For more information about how to use this structure, see <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/logging-errors">Logging Errors</a>.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ifs/irp-mj-device-control">IRP_MJ_DEVICE_CONTROL</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/irp-mj-internal-device-control">IRP_MJ_INTERNAL_DEVICE_CONTROL</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-ioallocateerrorlogentry">IoAllocateErrorLogEntry</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-iofreeerrorlogentry">IoFreeErrorLogEntry</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntifs/nf-ntifs-iowriteerrorlogentry">IoWriteErrorLogEntry</a>
 

 

