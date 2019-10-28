---
UID: NF:ntddk.MmAllocateContiguousMemorySpecifyCache
title: MmAllocateContiguousMemorySpecifyCache function (ntddk.h)
description: The MmAllocateContiguousMemorySpecifyCache routine allocates a range of contiguous, nonpaged physical memory and maps it to the system address space.
old-location: kernel\mmallocatecontiguousmemoryspecifycache.htm
tech.root: kernel
ms.assetid: e35544ed-d113-476e-85a8-6b3f613c1dc2
ms.date: 04/30/2018
ms.keywords: MmAllocateContiguousMemorySpecifyCache, MmAllocateContiguousMemorySpecifyCache routine [Kernel-Mode Driver Architecture], k106_764af538-9f9b-432b-af6a-4a6b7addd95d.xml, kernel.mmallocatecontiguousmemoryspecifycache, wdm/MmAllocateContiguousMemorySpecifyCache
ms.topic: function
f1_keywords:
 - "ntddk/MmAllocateContiguousMemorySpecifyCache"
req.header: ntddk.h
req.include-header: Wdm.h, Ntddk.h
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
req.irql: <= DISPATCH_LEVEL
topic_type:
- APIRef
- kbSyntax
api_type:
- DllExport
api_location:
- NtosKrnl.exe
api_name:
- MmAllocateContiguousMemorySpecifyCache
product:
- Windows
targetos: Windows
req.typenames: 
---

# MmAllocateContiguousMemorySpecifyCache function


## -description


The <b>MmAllocateContiguousMemorySpecifyCache</b> routine allocates a range of contiguous, nonpaged physical memory and maps it to the system address space.


## -parameters




### -param NumberOfBytes [in]

The size, in bytes, of the block of contiguous memory to allocate. For more information, see Remarks.


### -param LowestAcceptableAddress [in]

The lowest valid physical address the caller can use. For example, if a device can address only locations above the first 8 megabytes of the processor's physical memory address range, the driver for this device  should set <i>LowestAcceptableAddress</i> to 0x0000000000800000.


### -param HighestAcceptableAddress [in]

The highest valid physical address the caller can use. For example, if a device can address only locations in the first 16 megabytes of the processor's physical memory address range, the driver for this device should set <i>HighestAcceptableAddress</i> to 0x0000000000FFFFFF.


### -param BoundaryAddressMultiple [in, optional]

The physical address multiple that the allocated buffer must not cross. A physical address multiple must always be a power of two. This parameter is optional and can be specified as zero to indicate that the device has no special memory boundary restrictions. For more information, see Remarks.


### -param CacheType [in]

Specifies a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/ne-wdm-_memory_caching_type">MEMORY_CACHING_TYPE</a> value, which indicates the type of caching allowed for the requested memory.


## -returns



<b>MmAllocateContiguousMemorySpecifyCache</b> returns the base virtual address for the allocated memory. If the system is unable to allocate the requested buffer, the routine returns <b>NULL</b>.




## -remarks



<b>MmAllocateContiguousMemorySpecifyCache</b> allocates a block of nonpaged memory that is contiguous in physical address space. The routine maps this block to a contiguous block of virtual memory in the system address space and returns the virtual address of the base of this block. The routine aligns the starting address of a contiguous memory allocation to a memory page boundary.

Drivers must not access memory beyond the requested allocation size. For example, developers should not assume that their drivers can safely use memory between the end of their requested allocation and the next page boundary.

Because contiguous physical memory is usually in short supply, it should be used sparingly and only when necessary. A driver that must use contiguous memory should allocate this memory during driver initialization because physical memory is likely to become fragmented over time as the operating system allocates and frees memory. Typically, a driver calls <b>MmAllocateContiguousMemorySpecifyCache</b> from its <a href="https://docs.microsoft.com/windows-hardware/drivers/storage/driverentry-of-ide-controller-minidriver">DriverEntry</a> routine to allocate an internal buffer for long-term use, and frees the buffer just before the driver is unloaded.

Memory allocated by <b>MmAllocateContiguousMemorySpecifyCache</b> must be freed when the memory is no longer needed. Call the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-mmfreecontiguousmemory">MmFreeContiguousMemory</a> routine to free memory that is allocated by <b>MmAllocateContiguousMemorySpecifyCache</b>.

If you specify a nonzero value for the <i>BoundaryAddressMultiple</i> parameter, the physical address range of the allocated memory block will not cross an address boundary that is an integer multiple of this value. A driver should set this parameter to zero unless a nonzero value is required to work around a hardware limitation. For example, if a device cannot transfer data across 16-megabyte physical boundaries, the driver should specify a value of 0x1000000 for this parameter to ensure that the addresses that the device sees do not wrap around at a 16-megabyte boundary.

<div class="alert"><b>Note</b>  If you use the <b>MmAllocateContiguousMemorySpecifyCache</b> routine on computers with large amounts of memory, the operating system's performance might severely degrade when the system tries to create a contiguous chunk of memory. This degradation is greatly reduced starting with Windows Vista SP1 and Windows Server 2008, but contiguous memory can still be expensive to allocate. For this reason, drivers should avoid repeated calls to <b>MmAllocateContiguousMemorySpecifyCache</b>. Instead, drivers should allocate all required contiguous buffers in their <b>DriverEntry</b> routines and reuse these buffers.</div>
<div> </div>
<div class="alert"><b>Note</b>  Memory that <b>MmAllocateContiguousMemorySpecifyCache</b> allocates is uninitialized. A kernel-mode driver must first zero this memory if it is going to make it visible to user-mode software (to avoid leaking potentially privileged contents).</div>
<div> </div>



## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-mmallocatecontiguousmemory">MmAllocateContiguousMemory</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-mmfreecontiguousmemory">MmFreeContiguousMemory</a>
 

 

