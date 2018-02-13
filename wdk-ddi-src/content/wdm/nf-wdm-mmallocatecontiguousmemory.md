---
UID: NF:wdm.MmAllocateContiguousMemory
title: MmAllocateContiguousMemory function
author: windows-driver-content
description: The MmAllocateContiguousMemory routine allocates a range of contiguous, nonpaged physical memory and maps it to the system address space.
old-location: kernel\mmallocatecontiguousmemory.htm
old-project: kernel
ms.assetid: 45d5b640-5983-43cc-9b2e-2f2625dbd57c
ms.author: windowsdriverdev
ms.date: 1/4/2018
ms.keywords: k106_33fb6610-08f3-4605-9511-72a2ec6fa442.xml, MmAllocateContiguousMemory, MmAllocateContiguousMemory routine [Kernel-Mode Driver Architecture], wdm/MmAllocateContiguousMemory, kernel.mmallocatecontiguousmemory
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: wdm.h
req.include-header: Wdm.h
req.target-type: Universal
req.target-min-winverclnt: Available starting with Windows 2000.
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
req.lib: NtosKrnl.lib
req.dll: NtosKrnl.exe
req.irql: "<= DISPATCH_LEVEL"
topictype:
-	APIRef
-	kbSyntax
apitype:
-	DllExport
apilocation:
-	NtosKrnl.exe
apiname:
-	MmAllocateContiguousMemory
product: Windows
targetos: Windows
req.typenames: WORK_QUEUE_TYPE
req.product: Windows 10 or later.
---

# MmAllocateContiguousMemory function


## -description


The <b>MmAllocateContiguousMemory</b> routine allocates a range of contiguous, nonpaged physical memory and maps it to the system address space.


## -syntax


````
PVOID MmAllocateContiguousMemory(
  _In_ SIZE_T           NumberOfBytes,
  _In_ PHYSICAL_ADDRESS HighestAcceptableAddress
);
````


## -parameters




### -param NumberOfBytes [in]

The size, in bytes, of the block of contiguous memory to allocate. For more information, see Remarks.


### -param HighestAcceptableAddress [in]

The highest valid physical address the caller can use. For example, if a device can address only locations in the first 16 megabytes of the processor's physical memory address range, the driver for this device should set <i>HighestAcceptableAddress</i> to 0x0000000000FFFFFF.


## -returns



<b>MmAllocateContiguousMemory</b> returns the base virtual address for the allocated memory. If the request cannot be satisfied, the routine returns <b>NULL</b>.




## -remarks



<b>MmAllocateContiguousMemory</b> allocates a block of nonpaged memory that is contiguous in physical address space. The routine maps this block to a contiguous block of virtual memory in the system address space and returns the virtual address of the base of this block. The routine aligns the starting address of a contiguous memory allocation to a memory page boundary.

Drivers must not access memory beyond the requested allocation size. For example, developers should not assume that their drivers can safely use memory between the end of their requested allocation and the next page boundary.

Because contiguous physical memory is usually in short supply, it should be used sparingly and only when necessary. A driver that must use contiguous memory should allocate this memory during driver initialization because physical memory is likely to become fragmented over time as the operating system allocates and frees memory. Typically, a driver calls <b>MmAllocateContiguousMemory</b> from its <a href="..\wdm\nc-wdm-driver_initialize.md">DriverEntry</a> routine to allocate an internal buffer for long-term use, and frees the buffer just before the driver is unloaded.

Memory allocated by <b>MmAllocateContiguousMemory</b> must be freed when the memory is no longer needed. Call the <a href="..\wdm\nf-wdm-mmfreecontiguousmemory.md">MmFreeContiguousMemory</a> routine to free memory that is allocated by <b>MmAllocateContiguousMemory</b>.

<div class="alert"><b>Note</b>  When physical memory is fragmented on a computer that has a large amount of RAM, calls to <b>MmAllocateContiguousMemory</b>, which require the operating system to search for contiguous blocks of memory, can severely degrade performance. This degradation is greatly reduced starting with Windows Vista SP1 and Windows Server 2008, but contiguous memory can still be expensive to allocate. For this reason, drivers should avoid repeated calls to <b>MmAllocateContiguousMemory</b>. Instead, drivers should allocate all required contiguous buffers in their <b>DriverEntry</b> routines and reuse these buffers.<p class="note">Memory that <b>MmAllocateContiguousMemory</b> allocates is uninitialized. A kernel-mode driver must first set this memory to zero if it is going to make it visible to user-mode software (to avoid leaking potentially privileged contents).

</div>
<div> </div>



## -see-also

<a href="..\wdm\nf-wdm-mmallocatecontiguousmemoryspecifycache.md">MmAllocateContiguousMemorySpecifyCache</a>



<a href="..\ntddk\nf-ntddk-mmallocatenoncachedmemory.md">MmAllocateNonCachedMemory</a>



<a href="..\wdm\nc-wdm-pallocate_common_buffer.md">AllocateCommonBuffer</a>



<a href="..\wdm\nc-wdm-driver_initialize.md">DriverEntry</a>



<a href="..\wdm\nf-wdm-mmfreecontiguousmemory.md">MmFreeContiguousMemory</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20MmAllocateContiguousMemory routine%20 RELEASE:%20(1/4/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

