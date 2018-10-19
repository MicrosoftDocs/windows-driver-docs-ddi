---
UID: NF:wdm.MmAllocatePagesForMdlEx
title: MmAllocatePagesForMdlEx function
author: windows-driver-content
description: The MmAllocatePagesForMdlEx routine allocates nonpaged, physical memory pages to an MDL.
old-location: kernel\mmallocatepagesformdlex.htm
tech.root: kernel
ms.assetid: f860c230-01ca-4c7f-8b67-5d92a80ff906
ms.date: 04/30/2018
ms.keywords: MM_ALLOCATE_FROM_LOCAL_NODE_ONLY, MM_ALLOCATE_FULLY_REQUIRED, MM_ALLOCATE_NO_WAIT, MM_ALLOCATE_PREFER_CONTIGUOUS, MM_ALLOCATE_REQUIRE_CONTIGUOUS_CHUNKS, MM_DONT_ZERO_ALLOCATION, MmAllocatePagesForMdlEx, MmAllocatePagesForMdlEx routine [Kernel-Mode Driver Architecture], k106_df4d4bea-4360-4755-841c-f39849228e9b.xml, kernel.mmallocatepagesformdlex, wdm/MmAllocatePagesForMdlEx
ms.topic: function
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h
req.target-type: Universal
req.target-min-winverclnt: Available in Windows Server 2003 with Service Pack 1 (SP1) and later versions of Windows. You should use this routine instead of MmAllocatePagesForMdl on these operating systems.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: IrqlMmApcLte
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: NtosKrnl.lib
req.dll: NtosKrnl.exe
req.irql: See Remarks section.
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	DllExport
api_location:
-	NtosKrnl.exe
api_name:
-	MmAllocatePagesForMdlEx
product:
- Windows
targetos: Windows
req.typenames: 
---

# MmAllocatePagesForMdlEx function


## -description


The <b>MmAllocatePagesForMdlEx</b> routine allocates nonpaged, physical memory pages to an MDL.


## -parameters




### -param LowAddress [in]

Specifies the physical address of the start of the first address range from which the allocated pages can come. If <b>MmAllocatePagesForMdlEx</b> cannot allocate the requested number of bytes in the first address range, it iterates through additional address ranges to get more pages. At each iteration, <b>MmAllocatePagesForMdlEx</b> adds the value of <i>SkipBytes</i> to the previous start address to obtain the start of the next address range.


### -param HighAddress [in]

Specifies the physical address of the end of the first address range that the allocated pages can come from.


### -param SkipBytes [in]

Specifies the number of bytes to skip from the start of the previous address range that the allocated pages can come from. <i>SkipBytes</i> must be an integer multiple of the virtual memory page size, in bytes.


### -param TotalBytes [in]

Specifies the total number of bytes to allocate for the MDL.


### -param CacheType [in]

Specifies a <a href="https://msdn.microsoft.com/library/windows/hardware/ff554430">MEMORY_CACHING_TYPE</a> value, which indicates the type of caching that is allowed for the requested memory.


### -param Flags [in]

Specifies flags for this operation. Set this parameter to zero or to the bitwise OR of one or more of the following <b>MM_ALLOCATE_<i>XXX</i></b> flag bits:

The last four items in the preceding list are supported only in Windows 7 and later versions of Windows.

| **Value** | **Meaning** | 
|:--|:--|
| **MM_DONT_ZERO_ALLOCATION** 0x00000001|Do not fill the allocated pages with zeros. By default, MmAllocatePagesForMdlEx zeros the pages that it allocates. By skipping this operation, you can potentially improve the performance of the MmAllocatePagesForMdlEx call. However, you must not use this flag unless either you never expose the allocated pages to user-mode programs, or you always overwrite the original contents of the pages before you expose the allocated pages to user-mode programs. |
| **MM_ALLOCATE_FROM_LOCAL_NODE_ONLY** 0x00000002|Allocate pages only from the ideal node. This flag applies only to multiprocessor systems that have non-uniform memory access (NUMA) architectures. Starting with Windows Vista, this flag indicates that all pages must be allocated from the ideal node of the current thread. No pages are to be allocated from other nodes. In versions of Windows earlier than Windows Vista, this flag indicates that all pages must be allocated from the local node; that is, from the node that the current processor belongs to. For more information about NUMA multiprocessor systems, see [NUMA Support](http://go.microsoft.com/fwlink/p/?linkid=155041) . | 
| **MM_ALLOCATE_FULLY_REQUIRED** 0x00000004 |A full allocation is required. Starting with Windows 7, this flag requires MmAllocatePagesForMdlEx to return NULL if it cannot allocate all the requested pages. The routine returns a non-NULL value only if it successfully obtains the entire requested allocation. This flag enables the memory manager to perform the allocation more efficiently in cases in which the caller requires a full allocation. | 
| **MM_ALLOCATE_NO_WAIT** 0x00000008|Do not wait. Starting with Windows 7, this flag indicates that the MmAllocatePagesForMdlEx call must not block the calling thread. Typically, the caller is a kernel-mode driver that is running at IRQL < DISPATCH_LEVEL but cannot allow its execution to be blocked. For example, the driver might be assisting with paging or power-management operations. Regardless of whether this flag is set, MmAllocatePagesForMdlEx never blocks callers that are running at IRQL = DISPATCH_LEVEL. | 
| **MM_ALLOCATE_PREFER_CONTIGUOUS** 0x00000010 |Allocation is performed in a way that minimizes system memory fragmentation. Starting with Windows 7, this flag indicates that the caller wants to avoid fragmenting physical memory to make more contiguous memory available to other callers. The allocated pages are not guaranteed to be (and usually are not) physically contiguous, even if plenty of contiguous memory is available. Callers that require contiguous memory should specify MM_ALLOCATE_REQUIRE_CONTIGUOUS_CHUNKS instead of MM_ALLOCATE_PREFER_CONTIGUOUS. |
| **MM_ALLOCATE_REQUIRE_CONTIGUOUS_CHUNKS** 0x00000020 |Contiguous memory is required. Starting with Windows 7, this flag indicates that the requested pages must be allocated as contiguous blocks of physical memory. If the SkipBytes parameter is zero, MmAllocatePagesForMdlEx either succeeds and returns a single, contiguous block, or it fails and returns NULL. It never returns a partial allocation. For SkipBytes = 0, the allocated pages satisfy the address range requirements that are specified by the LowAddress and HighAddress parameters, but the pages are subject to no special alignment restrictions. If SkipBytes is nonzero, SkipBytes must be a power of two and must be greater than or equal to PAGE_SIZE, and the TotalBytes parameter value must be a multiple of SkipBytes. In this case, the returned MDL can contain multiple blocks of contiguous pages. That is, each block is internally contiguous but the blocks are not necessarily contiguous with each other. Each block of contiguous pages is guaranteed to be exactly SkipBytes long and to be aligned on a SkipBytes boundary. Partial allocations can occur if SkipBytes is nonzero, but each contiguous block in a partial allocation is guaranteed to be SkipBytes long. |
|**MM_ALLOCATE_FAST_LARGE_PAGES** 0x00000040| Starting with Windows 8, this flag specifies that the allocation must be satisfied from the operating system's large page cache. If the cache is empty, allocation fails.  If MM_ALLOCATE_FAST_LARGE_PAGES is not specified, **MmAllocatePagesForMdlEx** uses cached large pages if they are available. If the cache is exhausted, **MmAllocatePagesForMdlEx** attempts to construct additional large pages, which may take a long time. MM_ALLOCATE_FAST_LARGE_PAGES must be used  with the MM_ALLOCATE_REQUIRE_CONTIGUOUS_CHUNKS flag. The _SkipBytes_ parameter must be set to a multiple of large page size.|


## -returns



<b>MmAllocatePagesForMdlEx</b> returns one of the following:

<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>MDL pointer</b></dt>
</dl>
</td>
<td width="60%">
A non-<b>NULL</b> return value is a pointer to an MDL that describes a set of physical pages in the specified address range. If the requested number of bytes is not available, the MDL describes as much physical memory as is available.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b><b>NULL</b></b></dt>
</dl>
</td>
<td width="60%">
Indicates that no physical memory pages are available in the specified address ranges, or that there is not enough memory pool for the MDL itself.

</td>
</tr>
</table>
 




## -remarks



By default, the physical memory pages that <b>MmAllocatePagesForMdlEx</b> returns are not contiguous pages. Starting with Windows 7, callers can override the default behavior of this routine by setting the MM_ALLOCATE_PREFER_CONTIGUOUS or MM_ALLOCATE_REQUIRE_CONTIGUOUS_CHUNKS flag bit in the <i>Flags</i> parameter.

<b>MmAllocatePagesForMdlEx</b> is designed for kernel-mode drivers that do not need corresponding virtual addresses (that is, they need physical pages and do not need them to be physically contiguous), and for kernel-mode drivers that can achieve substantial performance gains if physical memory for a device is allocated in a specific physical address range (for example, an AGP graphics card).

Depending on how much physical memory is currently available in the requested ranges, <b>MmAllocatePagesForMdlEx</b> might return an MDL that describes less memory than was requested. The routine also might return <b>NULL</b> if no memory was allocated. The caller should check the amount of memory that is actually allocated to the MDL.

The caller must use <a href="https://msdn.microsoft.com/library/windows/hardware/ff554521">MmFreePagesFromMdl</a> to release the memory pages that are described by an MDL that was created by <b>MmAllocatePagesForMdlEx</b>. After calling <b>MmFreePagesFromMdl</b>, the caller must also call <a href="https://msdn.microsoft.com/library/windows/hardware/ff544590">ExFreePool</a> to release the memory that is allocated for the MDL structure.

By default, <b>MmAllocatePagesForMdlEx</b> fills the pages that it allocates with zeros. The caller can specify the MM_DONT_ZERO_ALLOCATION flag to override this default and to possibly improve performance.

<div class="alert"><b>Note</b>    Memory that <b>MmAllocatePagesForMdlEx</b> allocates is uninitialized if you specify the MM_DONT_ZERO_ALLOCATION flag. A kernel-mode driver must first zero this memory if the driver is going to make the memory visible to user-mode software (to avoid leaking potentially privileged contents). For more information about this flag, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff556396">MM_ALLOCATE_XXX</a>.</div>
<div> </div>
The maximum amount of memory that <b>MmAllocatePagesForMdlEx</b> can allocate in a single call is (4 gigabytes - PAGE_SIZE). The routine can satisfy an allocation request for this amount only if enough pages are available.

<b>MmAllocatePagesForMdlEx</b> runs at IRQL &lt;= APC_LEVEL. In Windows Server 2008 and later versions of Windows, callers of <b>MmAllocatePagesForMdlEx </b>are allowed to be at DISPATCH_LEVEL. However, you can improve driver performance by calling at APC_LEVEL or below.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff544590">ExFreePool</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff554430">MEMORY_CACHING_TYPE</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff554482">MmAllocatePagesForMdl</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff554521">MmFreePagesFromMdl</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff554622">MmMapLockedPages</a>
 

 

