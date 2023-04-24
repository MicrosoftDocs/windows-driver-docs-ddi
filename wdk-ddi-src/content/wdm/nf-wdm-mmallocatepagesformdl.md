---
UID: NF:wdm.MmAllocatePagesForMdl
title: MmAllocatePagesForMdl function (wdm.h)
description: The MmAllocatePagesForMdl routine allocates zero-filled, nonpaged, physical memory pages to an MDL.
tech.root: kernel
ms.date: 01/06/2023
keywords: ["MmAllocatePagesForMdl function"]
ms.keywords: MmAllocatePagesForMdl, MmAllocatePagesForMdl routine [Kernel-Mode Driver Architecture], k106_bb9bac91-62a6-45f8-9133-0d23eda07b1e.xml, kernel.mmallocatepagesformdl, wdm/MmAllocatePagesForMdl
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h
req.target-type: Universal
req.target-min-winverclnt:
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: IrqlMmApcLte, HwStorPortProhibitedDDIs, SpNoWait, StorPortStartIo
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
 - MmAllocatePagesForMdl
 - wdm/MmAllocatePagesForMdl
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - DllExport
api_location:
 - NtosKrnl.exe
api_name:
 - MmAllocatePagesForMdl
---

## -description

The **MmAllocatePagesForMdl** routine allocates zero-filled, non-paged, physical memory pages to an MDL.

## -parameters

### -param LowAddress [in]

Specifies the physical address of the start of the first address range from which the allocated pages can come. If **MmAllocatePagesForMdl** cannot allocate the requested number of bytes in the first address range, it iterates through additional address ranges to get more pages. At each iteration, **MmAllocatePagesForMdl** adds the value of *SkipBytes* to the previous start address to obtain the start of the next address range.

### -param HighAddress [in]

Specifies the physical address of the end of the first address range from which the allocated pages can come.

### -param SkipBytes [in]

Specifies the number of bytes to skip from the start of the previous address range from which the allocated pages can come. *SkipBytes* must be an integer multiple of the virtual memory page size, in bytes.

### -param TotalBytes [in]

Specifies the total number of bytes to allocate for the MDL.

## -returns

**MmAllocatePagesForMdl** returns one of the following:

| Return code | Description |
|---|---|
| **MDL pointer** | The MDL pointer describes a set of physical pages in the specified address range. If the requested number of bytes is not available, the MDL describes as much physical memory as is available. |
| **NULL** | There are no physical memory pages in the specified address ranges, or there is not enough memory pool for the MDL itself. |

## -remarks

Drivers that are running in Windows Server 2003 Service Pack 1 (SP1) and later versions of Windows should use the [MmAllocatePagesForMdlEx](./nf-wdm-mmallocatepagesformdlex.md) routine instead of **MmAllocatePagesForMdl**. **MmAllocatePagesForMdlEx** provides better performance than **MmAllocatePagesForMdl** by avoiding unnecessary flushes of the translation lookaside buffer (TLB) and cache memory.

The physical memory pages that are returned by **MmAllocatePagesForMdl** are typically not contiguous pages. **MmAllocatePagesForMdl** always fills the allocated pages in the returned MDL with zeros.

**MmAllocatePagesForMdl** is designed to be used by kernel-mode drivers that do not need corresponding virtual addresses (that is, they need physical pages and do not need the pages to be physically contiguous) or by kernel-mode drivers that can achieve substantial performance gains if physical memory for a device is allocated in a specific physical address range. A driver for an AGP graphics card is an example of such a driver.

Depending on how much physical memory is currently available in the requested ranges, **MmAllocatePagesForMdl** might return an MDL that describes less memory than was requested. The routine returns **NULL** if no memory was allocated. The caller should check the amount of memory that is actually allocated to the MDL.

The caller must use [MmFreePagesFromMdl](./nf-wdm-mmfreepagesfrommdl.md) to release the memory pages that are described by an MDL that was created by **MmAllocatePagesForMdl**. After calling **MmFreePagesFromMdl**, the caller must also call [ExFreePool](../ntddk/nf-ntddk-exfreepool.md) to release the memory that is allocated for the MDL structure itself.

In Windows 2000 and later versions of Windows, the maximum amount of memory that **MmAllocatePagesForMdl** can allocate in a single call is (4 gigabytes - PAGE_SIZE). The routine can satisfy an allocation request for this amount only if enough pages are available.

**MmAllocatePagesForMdl** runs at IRQL <= APC_LEVEL. Windows Server 2008 and later versions of the Windows operating system enable **MmAllocatePagesForMdl** callers to call at DISPATCH_LEVEL. However, you can improve driver performance by calling at APC_LEVEL or below.

Calling **MmAllocatePagesForMdl** from a special kernel asynchronous procedure call (APC) can lead to a recursive acquisition of an exclusive lock, which is only in a critical region (user or normal kernel APCs disabled) but not in a guarded region (all APCs disabled).

## -see-also

[ExFreePool](../ntddk/nf-ntddk-exfreepool.md)

[MmAllocatePagesForMdlEx](./nf-wdm-mmallocatepagesformdlex.md)

[MmFreePagesFromMdl](./nf-wdm-mmfreepagesfrommdl.md)

[MmMapLockedPages](./nf-wdm-mmmaplockedpages.md)
