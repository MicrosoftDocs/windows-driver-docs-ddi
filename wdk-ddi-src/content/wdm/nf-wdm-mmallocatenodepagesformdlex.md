---
UID: NF:wdm.MmAllocateNodePagesForMdlEx
title: MmAllocateNodePagesForMdlEx function (wdm.h)
description: The MmAllocateNodePagesForMdlEx routine allocates nonpaged physical memory from an ideal node, and allocates an MDL structure to describe this memory.
old-location: kernel\mmallocatenodepagesformdlex.htm
tech.root: kernel
ms.assetid: 491327A4-87B5-4206-9D47-007CE14E1327
ms.date: 04/30/2018
keywords: ["MmAllocateNodePagesForMdlEx function"]
ms.keywords: MmAllocateNodePagesForMdlEx, MmAllocateNodePagesForMdlEx routine [Kernel-Mode Driver Architecture], kernel.mmallocatenodepagesformdlex, wdm/MmAllocateNodePagesForMdlEx
f1_keywords:
 - "wdm/MmAllocateNodePagesForMdlEx"
 - "MmAllocateNodePagesForMdlEx"
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h
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
req.irql: <= DISPATCH_LEVEL (See Remarks section.)
topic_type:
- APIRef
- kbSyntax
api_type:
- DllExport
api_location:
- NtosKrnl.exe
api_name:
- MmAllocateNodePagesForMdlEx
product:
- Windows
targetos: Windows
req.typenames: 
---

# MmAllocateNodePagesForMdlEx function


## -description


The <b>MmAllocateNodePagesForMdlEx</b> routine allocates nonpaged physical memory from an ideal node, and allocates an <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/ns-wdm-_mdl">MDL</a> structure to describe this memory.


## -parameters




### -param LowAddress [in]

The physical address of the start of the first address range from which the allocated pages can come. If <b>MmAllocateNodePagesForMdlEx</b> cannot allocate the requested number of bytes in the first address range, the routine iterates through additional address ranges to get more pages. At each iteration, <b>MmAllocateNodePagesForMdlEx</b> adds the value of <i>SkipBytes</i> to the previous start address to calculate the start of the next address range.


### -param HighAddress [in]

The physical address of the end of the first address range that the allocated pages can come from.


### -param SkipBytes [in]

The number of bytes to skip from the start of the previous address range that the allocated pages can come from. <i>SkipBytes</i> must be an integer multiple of the virtual memory page size, in bytes.


### -param TotalBytes [in]

The total number of bytes to allocate for the MDL.


### -param CacheType [in]

A <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/ne-wdm-_memory_caching_type">MEMORY_CACHING_TYPE</a> value, which indicates the type of caching that is allowed for the requested memory.


### -param IdealNode [in]

The ideal node number. If a multiprocessor system contains N nodes, valid node numbers are in the range 0 to N-1. Your driver can call the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddk/nf-ntddk-kequeryhighestnodenumber">KeQueryHighestNodeNumber</a> routine to get the highest node number. A single-processor or non-NUMA multiprocessor system has only one node, node 0, from which to allocate memory. For a NUMA multiprocessor system, the allocation is made from the ideal node, if possible. If insufficient memory is available in the ideal node to satisfy the allocation request, and the caller does not set the MM_ALLOCATE_FROM_LOCAL_NODE_ONLY flag, <b>MmAllocateNodePagesForMdlEx</b> will try to allocate memory from other nodes.


### -param Flags [in]

Flags for this operation. Set this parameter to zero or to the bitwise-OR of one or more of the following flag bits:

<ul>
<li>
MM_DONT_ZERO_ALLOCATION

</li>
<li>
MM_ALLOCATE_FROM_LOCAL_NODE_ONLY

</li>
<li>
MM_ALLOCATE_FULLY_REQUIRED

</li>
<li>
MM_ALLOCATE_NO_WAIT

</li>
<li>
MM_ALLOCATE_PREFER_CONTIGUOUS

</li>
<li>
MM_ALLOCATE_REQUIRE_CONTIGUOUS_CHUNKS

</li>
</ul>
The MM_ALLOCATE_PREFER_CONTIGUOUS and MM_ALLOCATE_REQUIRE_CONTIGUOUS_CHUNKS flag bits are mutually exclusive. For more information about these flags, see <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-mmallocatepagesformdlex">MM_ALLOCATE_XXX</a>.


## -returns



<b>MmAllocateNodePagesForMdlEx</b> returns a pointer to an MDL structure if it is successful. Otherwise, if the routine fails to allocate any memory, the routine returns <b>NULL</b>.

A return value of <b>NULL</b> indicates that no physical memory pages are available in the specified address ranges, or that there is not enough memory pool available to allocate the MDL structure.

If the routine successfully allocates some, but not all, of the requested memory, the MDL describes as much physical memory as the routine was able to allocate.




## -remarks



In a non-uniform memory access (NUMA) multiprocessor system, the caller can specify an ideal node from which to allocate the memory. A node is a collection of processors that share fast access to a region of memory. In a non-NUMA multiprocessor or a single-processor system, <b>MmAllocateNodePagesForMdlEx</b> treats all memory as belonging to a single node and allocates memory from this node.

By default, the physical memory pages that <b>MmAllocateNodePagesForMdlEx</b> returns are not contiguous pages. Callers can override the default behavior of this routine by setting the MM_ALLOCATE_PREFER_CONTIGUOUS or MM_ALLOCATE_REQUIRE_CONTIGUOUS_CHUNKS flag bit in the <i>Flags</i> parameter.

<b>MmAllocateNodePagesForMdlEx</b> does not map the allocated physical memory into virtual memory. If necessary, the caller can call a routine such as <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-mmmaplockedpagesspecifycache">MmMapLockedPagesSpecifyCache</a> to map the physical memory pages described by the MDL.

<b>MmAllocateNodePagesForMdlEx</b> is designed for kernel-mode drivers that do not need corresponding virtual addresses (that is, they need physical pages and do not need them to be physically contiguous), and for kernel-mode drivers that can achieve substantial performance gains if physical memory for a device is allocated in a specific physical address range (for example, an AGP graphics card).

Depending on how much physical memory is currently available in the requested ranges, <b>MmAllocateNodePagesForMdlEx</b> might return an MDL that describes less memory than was requested. The routine also might return <b>NULL</b> if no memory was allocated. The caller should check the amount of memory that is actually allocated, as described by the MDL.

The caller must use <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-mmfreepagesfrommdl">MmFreePagesFromMdl</a> to release the memory pages that are described by an MDL that was created by <b>MmAllocateNodePagesForMdlEx</b>. After calling <b>MmFreePagesFromMdl</b>, the caller must also call <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddk/nf-ntddk-exfreepool">ExFreePool</a> to release the memory allocated for the MDL structure.

By default, <b>MmAllocateNodePagesForMdlEx</b> fills the pages that it allocates with zeros. The caller can specify the MM_DONT_ZERO_ALLOCATION flag to override this default and to possibly improve performance.

<div class="alert"><b>Note</b>    Memory that <b>MmAllocateNodePagesForMdlEx</b> allocates is uninitialized if you specify the MM_DONT_ZERO_ALLOCATION flag. A kernel-mode driver must first zero this memory if the driver is going to make the memory visible to user-mode software (to avoid leaking potentially privileged contents). For more information about this flag, see <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-mmallocatepagesformdlex">MM_ALLOCATE_XXX</a>.</div>
<div> </div>
The maximum amount of memory that <b>MmAllocateNodePagesForMdlEx</b> can allocate in a single call is (4 gigabytes - PAGE_SIZE). The routine can satisfy an allocation request for this amount only if enough pages are available.

<b>MmAllocateNodePagesForMdlEx</b> runs at IRQL <= APC_LEVEL. If necessary, your driver can call <b>MmAllocateNodePagesForMdlEx</b> at DISPATCH_LEVEL. However, you can improve driver performance by calling at APC_LEVEL or below.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddk/nf-ntddk-exfreepool">ExFreePool</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddk/nf-ntddk-kequeryhighestnodenumber">KeQueryHighestNodeNumber</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/ns-wdm-_mdl">MDL</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/ne-wdm-_memory_caching_type">MEMORY_CACHING_TYPE</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-mmallocatepagesformdlex">MM_ALLOCATE_XXX</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-mmfreepagesfrommdl">MmFreePagesFromMdl</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-mmmaplockedpagesspecifycache">MmMapLockedPagesSpecifyCache</a>
 

 

