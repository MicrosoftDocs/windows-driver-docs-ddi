---
UID: NF:ntddk.MmAllocateContiguousNodeMemory
title: MmAllocateContiguousNodeMemory function (ntddk.h)
description: The MmAllocateContiguousNodeMemory routine allocates a range of contiguous, nonpaged physical memory and maps it to the system address space.
old-location: kernel\mmallocatecontiguousnodememory.htm
tech.root: kernel
ms.assetid: 08960797-4846-46D4-8DD9-3A935EAD7D48
ms.date: 04/30/2018
ms.keywords: MmAllocateContiguousNodeMemory, MmAllocateContiguousNodeMemory routine [Kernel-Mode Driver Architecture], kernel.mmallocatecontiguousnodememory, wdm/MmAllocateContiguousNodeMemory
f1_keywords:
 - "ntddk/MmAllocateContiguousNodeMemory"
req.header: ntddk.h
req.include-header: Wdm.h, Ntddk.h
req.target-type: Universal
req.target-min-winverclnt: Available starting with Windows 8.
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
- MmAllocateContiguousNodeMemory
product:
- Windows
targetos: Windows
req.typenames: 
---

# MmAllocateContiguousNodeMemory function


## -description


The <b>MmAllocateContiguousNodeMemory</b> routine allocates a range of contiguous, nonpaged physical memory and maps it to the system address space.


## -parameters




### -param NumberOfBytes [in]

The size, in bytes, of the block of contiguous memory to allocate. For more information, see Remarks.


### -param LowestAcceptableAddress [in]

The lowest valid physical address the caller can use. For example, if a device can address only locations above the first 8 megabytes of the processor's physical memory address range, the driver for this device  should set <i>LowestAcceptableAddress</i> to 0x0000000000800000.


### -param HighestAcceptableAddress [in]

The highest valid physical address the caller can use. For example, if a device can address only locations in the first 16 megabytes of the processor's physical memory address range, the driver for this device should set <i>HighestAcceptableAddress</i> to 0x0000000000FFFFFF.


### -param BoundaryAddressMultiple [in, optional]

The physical address multiple that the allocated buffer must not cross. A physical address multiple must always be a power of two. This parameter is optional and can be specified as zero to indicate that the device has no special memory boundary restrictions. For more information, see Remarks.


### -param Protect [in]

Flag bits that specify the protection to use for the allocated memory. The caller must set one (but not both) of the following flag bits in the <i>Protect</i> parameter.

<table>
<tr>
<th>Flag bit</th>
<th>Meaning</th>
</tr>
<tr>
<td>PAGE_READWRITE</td>
<td>Allocate read/write, no-execute (NX) memory. Most callers should set this flag bit. For more information, see Remarks.</td>
</tr>
<tr>
<td>PAGE_EXECUTE_READWRITE</td>
<td>Allocate read/write memory that is executable. This flag bit should be set only if the caller requires the ability to execute instructions in the allocated memory.</td>
</tr>
</table>
 

In addition, the caller can set one (but not both) of the following optional flag bits in the <i>Protect</i> parameter.

<table>
<tr>
<th>Flag bit</th>
<th>Meaning</th>
</tr>
<tr>
<td>PAGE_NOCACHE</td>
<td>Allocate non-cached memory. This flag bit is similar in effect to calling <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-mmallocatecontiguousmemoryspecifycache">MmAllocateContiguousMemorySpecifyCache</a> with <i>CacheType</i> set to <b>MmNonCached</b>.</td>
</tr>
<tr>
<td>PAGE_WRITECOMBINE</td>
<td>Allocate write-combined memory. This flag bit is similar in effect to calling <b>MmAllocateContiguousMemorySpecifyCache</b> with <i>CacheType</i> set to <b>MmWriteCombined</b>.</td>
</tr>
</table>
 

If neither PAGE_NOCACHE nor PAGE_WRITECOMBINE is specified, the allocated memory is fully cached. In this case, the effect is similar to calling <b>MmAllocateContiguousMemorySpecifyCache</b> with <i>CacheType</i> set to <b>MmCached</b>.


### -param PreferredNode [in]

The preferred node number. If a multiprocessor system contains N nodes, the nodes are numbered from 0 to N-1. If the caller sets <i>PreferredNode</i> to MM_ANY_NODE_OK, the routine chooses which node to allocate memory from. Otherwise, if memory in the specified address range cannot be allocated from the preferred node, the routine returns <b>NULL</b>.


## -returns



<b>MmAllocateContiguousNodeMemory</b> returns the base virtual address for the allocated memory. If the request cannot be satisfied, the routine returns <b>NULL</b>.




## -remarks



A kernel-mode device driver calls this routine  to allocate a contiguous block of physical memory. The calling driver can specify whether to use no-execute (NX) memory for the allocation. In a non-uniform memory access (NUMA) multiprocessor system, the caller can specify a preferred node from which to allocate the memory. A node is a collection of processors that share fast access to a region of memory. In a non-NUMA multiprocessor or a single-processor system, <b>MmAllocateContiguousNodeMemory</b> treats all memory as belonging to a single node and allocates memory from this node.

<b>MmAllocateContiguousNodeMemory</b> allocates a block of nonpaged memory that is contiguous in physical address space. The routine maps this block to a contiguous block of virtual memory in the system address space and returns the virtual address of the base of this block. The routine aligns the starting address of a contiguous memory allocation to a memory page boundary.

Drivers must not access memory beyond the requested allocation size. For example, developers should not assume that their drivers can safely use memory between the end of their requested allocation and the next page boundary.

Because contiguous physical memory is usually in short supply, it should be used sparingly and only when necessary. A driver that must use contiguous memory should allocate this memory during driver initialization because physical memory is likely to become fragmented over time as the operating system allocates and frees memory. Typically, a driver calls <b>MmAllocateContiguousNodeMemory</b> from its <a href="https://docs.microsoft.com/windows-hardware/drivers/storage/driverentry-of-ide-controller-minidriver">DriverEntry</a> routine to allocate an internal buffer for long-term use, and frees the buffer just before the driver is unloaded.

Memory allocated by <b>MmAllocateContiguousNodeMemory</b> must be freed when the memory is no longer needed. Call the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-mmfreecontiguousmemory">MmFreeContiguousMemory</a> routine to free memory that is allocated by <b>MmAllocateContiguousNodeMemory</b>.

<b>MmAllocateContiguousNodeMemory</b> is similar to the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-mmallocatecontiguousmemoryspecifycachenode">MmAllocateContiguousMemorySpecifyCacheNode</a> routine. Unlike <b>MmAllocateContiguousMemorySpecifyCacheNode</b>, <b>MmAllocateContiguousNodeMemory</b> can be used to allocate no-execute (NX) memory. As a best practice, a driver should allocate NX memory unless the driver explicitly requires the ability to execute instructions in the allocated memory. By allocating NX memory, a driver improves security by preventing malicious software from executing instructions in this memory. Memory allocated by the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-mmallocatecontiguousmemory">MmAllocateContiguousMemory</a>, <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-mmallocatecontiguousmemoryspecifycache">MmAllocateContiguousMemorySpecifyCache</a>, and <b>MmAllocateContiguousMemorySpecifyCacheNode</b> routines is always executable.

If you specify a nonzero value for the <i>BoundaryAddressMultiple</i> parameter, the physical address range of the allocated memory block will not cross an address boundary that is an integer multiple of this value. A driver should set this parameter to zero unless a nonzero value is required to work around a hardware limitation. For example, if a device cannot transfer data across 16-megabyte physical boundaries, the driver should specify a value of 0x1000000 for this parameter to ensure that the addresses that the device sees do not wrap around at a 16-megabyte boundary.

<div class="alert"><b>Note</b>  Memory that <b>MmAllocateContiguousNodeMemory</b> allocates is uninitialized. A kernel-mode driver must first zero this memory if it is going to make it visible to user-mode software (to avoid leaking potentially privileged contents).</div>
<div> </div>



## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/storage/driverentry-of-ide-controller-minidriver">DriverEntry</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-mmallocatecontiguousmemory">MmAllocateContiguousMemory</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-mmallocatecontiguousmemoryspecifycache">MmAllocateContiguousMemorySpecifyCache</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-mmallocatecontiguousmemoryspecifycachenode">MmAllocateContiguousMemorySpecifyCacheNode</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-mmfreecontiguousmemory">MmFreeContiguousMemory</a>
 

 

