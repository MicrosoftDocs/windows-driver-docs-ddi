---
UID: NF:ntddk.KeQueryHardwareCounterConfiguration
title: KeQueryHardwareCounterConfiguration function
author: windows-driver-content
description: The KeQueryHardwareCounterConfiguration routine queries the operating system for the list of hardware counters to use for thread profiling.
old-location: kernel\kequeryhardwarecounterconfiguration.htm
old-project: kernel
ms.assetid: 5ac33177-38fc-4027-95c9-c2cf9ccdaa52
ms.author: windowsdriverdev
ms.date: 1/4/2018
ms.keywords: KeQueryHardwareCounterConfiguration
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: ntddk.h
req.include-header: Ntddk.h
req.target-type: Universal
req.target-min-winverclnt: Available in Windows 7 and later versions of Windows.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: KeQueryHardwareCounterConfiguration
req.alt-loc: NtosKrnl.exe
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: NtosKrnl.lib
req.dll: NtosKrnl.exe
req.irql: <= APC_LEVEL
req.typenames: WHEA_RAW_DATA_FORMAT, *PWHEA_RAW_DATA_FORMAT
---

# KeQueryHardwareCounterConfiguration function



## -description
The <b>KeQueryHardwareCounterConfiguration</b> routine queries the operating system for the list of hardware counters to use for thread profiling. 



## -syntax

````
NTSTATUS KeQueryHardwareCounterConfiguration(
  _Out_ PHARDWARE_COUNTER CounterArray,
  _In_  ULONG             MaximumCount,
  _Out_ PULONG            Count
);
````


## -parameters

### -param CounterArray [out]

A pointer to a caller-allocated buffer into which the routine writes an array of elements of type <a href="..\ntddk\ns-ntddk-_hardware_counter.md">HARDWARE_COUNTER</a>. Each array element is a structure that contains information about a hardware counter. The array contains one element for each hardware counter that is assigned to thread profiling. If the routine fails, it writes nothing to this buffer. 


### -param MaximumCount [in]

Specifies the maximum number of elements that the routine can write to the buffer that is pointed to by the <i>CounterArray</i> parameter. The size of the caller-allocated buffer must be at least <i>MaximumCount</i> * <b>sizeof</b>(<b>HARDWARE_COUNTER</b>) bytes. 


### -param Count [out]

A pointer to a location into which the routine writes the number of array elements that it has written to the buffer that is pointed to by the <i>CounterArray</i> parameter. If the buffer length that is specified by <i>MaximumCount</i> is not large enough to contain the entire array, the routine writes the required length to *<i>Count</i> and returns STATUS_BUFFER_TOO_SMALL. 


## -returns
<b>KeQueryHardwareCounterConfiguration</b> returns STATUS_SUCCESS if the call is successful. Possible error return values include the following:
<dl>
<dt><b>STATUS_BUFFER_TOO_SMALL</b></dt>
</dl>The <i>MaximumCount</i> parameter specifies a buffer length that is not large enough to contain the counter configuration information. 
<dl>
<dt><b>STATUS_NOT_IMPLEMENTED</b></dt>
</dl>This routine is not implemented for the processor architecture that the caller is running on. 

 


## -remarks
In Windows 7, this routine is implemented only for the x86-based, x64-based, and Itanium-based architectures. If the caller is running on a processor architecture that is not supported, the routine returns STATUS_NOT_IMPLEMENTED. 

To set the hardware counter configuration to use for thread profiling, call the <a href="..\ntddk\nf-ntddk-kesethardwarecounterconfiguration.md">KeSetHardwareCounterConfiguration</a> routine. 


## -see-also
<dl>
<dt>
<a href="..\ntddk\ns-ntddk-_hardware_counter.md">HARDWARE_COUNTER</a>
</dt>
<dt>
<a href="..\ntddk\nf-ntddk-kesethardwarecounterconfiguration.md">KeSetHardwareCounterConfiguration</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20KeQueryHardwareCounterConfiguration routine%20 RELEASE:%20(1/4/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

