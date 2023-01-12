---
UID: NF:wdm.MmAllocatePagesForMdlEx
title: MmAllocatePagesForMdlEx function (wdm.h)
description: The MmAllocatePagesForMdlEx routine allocates nonpaged, physical memory pages to an MDL. Use this routine instead of MmAllocatePagesForMdl.
tech.root: kernel
ms.date: 12/13/2022
keywords: ["MmAllocatePagesForMdlEx function"]
ms.keywords: MM_ALLOCATE_FROM_LOCAL_NODE_ONLY, MM_ALLOCATE_FULLY_REQUIRED, MM_ALLOCATE_NO_WAIT, MM_ALLOCATE_PREFER_CONTIGUOUS, MM_ALLOCATE_REQUIRE_CONTIGUOUS_CHUNKS, MM_DONT_ZERO_ALLOCATION, MmAllocatePagesForMdlEx, MmAllocatePagesForMdlEx routine [Kernel-Mode Driver Architecture], k106_df4d4bea-4360-4755-841c-f39849228e9b.xml, kernel.mmallocatepagesformdlex, wdm/MmAllocatePagesForMdlEx
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h
req.target-type: Universal
req.target-min-winverclnt: 
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
targetos: Windows
req.typenames: 
f1_keywords:
 - MmAllocatePagesForMdlEx
 - wdm/MmAllocatePagesForMdlEx
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - DllExport
api_location:
 - NtosKrnl.exe
api_name:
 - MmAllocatePagesForMdlEx
---

## -description

The **MmAllocatePagesForMdlEx** routine allocates nonpaged, physical memory pages to an MDL.

Use this routine instead of MmAllocatePagesForMdl.

## -parameters

### -param LowAddress [in]

Specifies the physical address of the start of the first address range from which the allocated pages can come. If **MmAllocatePagesForMdlEx** cannot allocate the requested number of bytes in the first address range, it iterates through additional address ranges to get more pages. At each iteration, **MmAllocatePagesForMdlEx** adds the value of *SkipBytes* to the previous start address to obtain the start of the next address range.

### -param HighAddress [in]

Specifies the physical address of the end of the first address range that the allocated pages can come from.

### -param SkipBytes [in]

Specifies the number of bytes to skip from the start of the previous address range that the allocated pages can come from. *SkipBytes* must be an integer multiple of the virtual memory page size, in bytes.

### -param TotalBytes [in]

Specifies the total number of bytes to allocate for the MDL.

### -param CacheType [in]

Specifies a [MEMORY_CACHING_TYPE](./ne-wdm-_memory_caching_type.md) value, which indicates the type of caching that is allowed for the requested memory.

### -param Flags [in]

Specifies flags for this operation. Set this parameter to zero or to the bitwise OR of one or more of the following **MM_ALLOCATE_*XXX*** flag bits:

The last four items in the preceding list are supported only in Windows 7 and later versions of Windows.

| Value | Meaning |  
|---|---|
| **MM_DONT_ZERO_ALLOCATION** 0x00000001 | Do not fill the allocated pages with zeros. By default, MmAllocatePagesForMdlEx zeros the pages that it allocates. By skipping this operation, you can potentially improve the performance of the MmAllocatePagesForMdlEx call. However, you must not use this flag unless either you never expose the allocated pages to user-mode programs, or you always overwrite the original contents of the pages before you expose the allocated pages to user-mode programs. |
| **MM_ALLOCATE_FROM_LOCAL_NODE_ONLY** 0x00000002 | Allocate pages only from the ideal node. This flag applies only to multiprocessor systems that have non-uniform memory access (NUMA) architectures. Starting with Windows Vista, this flag indicates that all pages must be allocated from the ideal node of the current thread. No pages are to be allocated from other nodes. In versions of Windows earlier than Windows Vista, this flag indicates that all pages must be allocated from the local node; that is, from the node that the current processor belongs to. For more information about NUMA multiprocessor systems, see [NUMA Support](/windows/win32/procthread/numa-support) . |  
| **MM_ALLOCATE_FULLY_REQUIRED** 0x00000004 | A full allocation is required. Starting with Windows 7, this flag requires MmAllocatePagesForMdlEx to return NULL if it cannot allocate all the requested pages. The routine returns a non-NULL value only if it successfully obtains the entire requested allocation. This flag enables the memory manager to perform the allocation more efficiently in cases in which the caller requires a full allocation. |  
| **MM_ALLOCATE_NO_WAIT** 0x00000008 | Do not wait. Starting with Windows 7, this flag indicates that the MmAllocatePagesForMdlEx call must not block the calling thread. Typically, the caller is a kernel-mode driver that is running at IRQL < DISPATCH_LEVEL but cannot allow its execution to be blocked. For example, the driver might be assisting with paging or power-management operations. Regardless of whether this flag is set, MmAllocatePagesForMdlEx never blocks callers that are running at IRQL = DISPATCH_LEVEL. |  
| **MM_ALLOCATE_PREFER_CONTIGUOUS** 0x00000010 | Allocation is performed in a way that minimizes system memory fragmentation. Starting with Windows 7, this flag indicates that the caller wants to avoid fragmenting physical memory to make more contiguous memory available to other callers. The allocated pages are not guaranteed to be (and usually are not) physically contiguous, even if plenty of contiguous memory is available. Callers that require contiguous memory should specify MM_ALLOCATE_REQUIRE_CONTIGUOUS_CHUNKS instead of MM_ALLOCATE_PREFER_CONTIGUOUS. |
| **MM_ALLOCATE_REQUIRE_CONTIGUOUS_CHUNKS** 0x00000020 | Contiguous memory is required. Starting with Windows 7, this flag indicates that the requested pages must be allocated as contiguous blocks of physical memory. If the SkipBytes parameter is zero, MmAllocatePagesForMdlEx either succeeds and returns a single, contiguous block, or it fails and returns NULL. It never returns a partial allocation. For SkipBytes = 0, the allocated pages satisfy the address range requirements that are specified by the LowAddress and HighAddress parameters, but the pages are subject to no special alignment restrictions. If SkipBytes is nonzero, SkipBytes must be a power of two and must be greater than or equal to PAGE_SIZE, and the TotalBytes parameter value must be a multiple of SkipBytes. In this case, the returned MDL can contain multiple blocks of contiguous pages. That is, each block is internally contiguous but the blocks are not necessarily contiguous with each other. Each block of contiguous pages is guaranteed to be exactly SkipBytes long and to be aligned on a SkipBytes boundary. Partial allocations can occur if SkipBytes is nonzero, but each contiguous block in a partial allocation is guaranteed to be SkipBytes long. |
| **MM_ALLOCATE_FAST_LARGE_PAGES** 0x00000040 | Starting with Windows 8, this flag specifies that the allocation must be satisfied from the operating system's large page cache. If the cache is empty, allocation fails.  If MM_ALLOCATE_FAST_LARGE_PAGES is not specified, **MmAllocatePagesForMdlEx** uses cached large pages if they are available. If the cache is exhausted, **MmAllocatePagesForMdlEx** attempts to construct additional large pages, which may take a long time. MM_ALLOCATE_FAST_LARGE_PAGES must be used  with the MM_ALLOCATE_REQUIRE_CONTIGUOUS_CHUNKS flag. The *SkipBytes* parameter must be set to a multiple of large page size. |

## -returns

**MmAllocatePagesForMdlEx** returns one of the following:

| Return code | Description |
|---|---|
| **MDL pointer** | A non-**NULL** return value is a pointer to an MDL that describes a set of physical pages in the specified address range. If the requested number of bytes is not available, the MDL describes as much physical memory as is available. |
| **NULL** | Indicates that no physical memory pages are available in the specified address ranges, or that there is not enough memory pool for the MDL itself. |

## -remarks

By default, the physical memory pages that **MmAllocatePagesForMdlEx** returns are not contiguous pages. Starting with Windows 7, callers can override the default behavior of this routine by setting the MM_ALLOCATE_PREFER_CONTIGUOUS or MM_ALLOCATE_REQUIRE_CONTIGUOUS_CHUNKS flag bit in the *Flags* parameter.

**MmAllocatePagesForMdlEx** is designed for kernel-mode drivers that do not need corresponding virtual addresses (that is, they need physical pages and do not need them to be physically contiguous), and for kernel-mode drivers that can achieve substantial performance gains if physical memory for a device is allocated in a specific physical address range (for example, an AGP graphics card).

Depending on how much physical memory is currently available in the requested ranges, **MmAllocatePagesForMdlEx** might return an MDL that describes less memory than was requested. The routine also might return **NULL** if no memory was allocated. The caller should check the amount of memory that is actually allocated to the MDL.

The caller must use [MmFreePagesFromMdl](./nf-wdm-mmfreepagesfrommdl.md) to release the memory pages that are described by an MDL that was created by **MmAllocatePagesForMdlEx**. After calling **MmFreePagesFromMdl**, the caller must also call [ExFreePool](../ntddk/nf-ntddk-exfreepool.md) to release the memory that is allocated for the MDL structure.

By default, **MmAllocatePagesForMdlEx** fills the pages that it allocates with zeros. The caller can specify the MM_DONT_ZERO_ALLOCATION flag to override this default and to possibly improve performance.

Memory that **MmAllocatePagesForMdlEx** allocates is uninitialized if you specify the MM_DONT_ZERO_ALLOCATION flag. A kernel-mode driver must first zero this memory if the driver is going to make the memory visible to user-mode software (to avoid leaking potentially privileged contents). For more information about this flag, see [MM_ALLOCATE_XXX](/windows-hardware/drivers/ddi/wdm/nf-wdm-mmallocatepagesformdlex).

The maximum amount of memory that **MmAllocatePagesForMdlEx** can allocate in a single call is (4 gigabytes - PAGE_SIZE). The routine can satisfy an allocation request for this amount only if enough pages are available.

**MmAllocatePagesForMdlEx** runs at IRQL <= APC_LEVEL. Callers of **MmAllocatePagesForMdlEx** are allowed to be at DISPATCH_LEVEL. However, you can improve driver performance by calling at APC_LEVEL or below.

## -see-also

[ExFreePool](../ntddk/nf-ntddk-exfreepool.md)

[MEMORY_CACHING_TYPE](./ne-wdm-_memory_caching_type.md)

[MmAllocatePagesForMdl](./nf-wdm-mmallocatepagesformdl.md)

[MmFreePagesFromMdl](./nf-wdm-mmfreepagesfrommdl.md)

[MmMapLockedPages](./nf-wdm-mmmaplockedpages.md)