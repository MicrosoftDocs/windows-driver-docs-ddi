---
UID: NF:wdm.MmMapLockedPagesWithReservedMapping
title: MmMapLockedPagesWithReservedMapping function (wdm.h)
description: The MmMapLockedPagesWithReservedMapping routine maps all or part of an address range that was previously reserved by the MmAllocateMappingAddress routine.
old-location: kernel\mmmaplockedpageswithreservedmapping.htm
tech.root: kernel
ms.date: 08/09/2021
keywords: ["MmMapLockedPagesWithReservedMapping function"]
ms.keywords: MmMapLockedPagesWithReservedMapping, MmMapLockedPagesWithReservedMapping routine [Kernel-Mode Driver Architecture], k106_32161803-dd44-4a5f-a5c0-da6b1a78982c.xml, kernel.mmmaplockedpageswithreservedmapping, wdm/MmMapLockedPagesWithReservedMapping
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h
req.target-type: Universal
req.target-min-winverclnt: Available in Windows XP and later versions of Windows.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: HwStorPortProhibitedDDIs
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: NtosKrnl.lib
req.dll: NtosKrnl.exe
req.irql: <= DISPATCH_LEVEL
targetos: Windows
req.typenames: 
f1_keywords:
 - MmMapLockedPagesWithReservedMapping
 - wdm/MmMapLockedPagesWithReservedMapping
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - DllExport
api_location:
 - NtosKrnl.exe
api_name:
 - MmMapLockedPagesWithReservedMapping
---

# MmMapLockedPagesWithReservedMapping function

## -description

The **MmMapLockedPagesWithReservedMapping** routine maps all or part of an address range that was previously reserved by the [MmAllocateMappingAddress](./nf-wdm-mmallocatemappingaddress.md) routine.

## -parameters

### -param MappingAddress

[in] Pointer to the beginning of the reserved virtual memory range. This must be an address previously returned by [MmAllocateMappingAddress](./nf-wdm-mmallocatemappingaddress.md).

### -param PoolTag

[in] Specifies the pool tag for the reserved memory buffer. This must be identical to the value specified in the *PoolTag* parameter of the call to [MmAllocateMappingAddress](./nf-wdm-mmallocatemappingaddress.md) that reserved the buffer.

### -param MemoryDescriptorList

[in] A pointer to the MDL that is to be mapped. This MDL must describe physical pages that are locked down. A locked-down MDL can be built by the [MmProbeAndLockPages](./nf-wdm-mmprobeandlockpages.md) or [MmAllocatePagesForMdlEx](./nf-wdm-mmallocatepagesformdlex.md) routine.

### -param CacheType

[in] Specifies the [MEMORY_CACHING_TYPE](./ne-wdm-_memory_caching_type.md) value to use to create the mapping.

## -returns

**MmMapLockedPagesWithReservedMapping** returns a pointer to the beginning of the mapped memory, or **NULL** if the system could not map the memory. This routine returns **NULL** only if there is an error in the function parameters (for example, the driver's mapping address is not large enough to span the supplied MDL). This function is intended to enable drivers to make forward progress even in low-resource scenarios.

## -remarks

The caller can use **MmMapLockedPagesWithReservedMapping** to map a subrange of the virtual memory range reserved by [MmAllocateMappingAddress](./nf-wdm-mmallocatemappingaddress.md) as follows:

- Use [IoAllocateMdl](./nf-wdm-ioallocatemdl.md) to allocate an MDL. The returned MDL is built using the specified starting address and size of the subrange of the virtual memory range to map.

- Use [MmProbeAndLockPages](./nf-wdm-mmprobeandlockpages.md) to lock down the physical pages described by the MDL obtained in step 1.

- Use **MmMapLockedPagesWithReservedMapping** to actually map the virtual memory to the physical memory that was locked down in step 2. Note that the virtual address returned by this function does include the byte offset that the MDL specifies. However, the **MappedSystemVa** field of the MDL that is set by this function does not include the byte offset.

- Once the caller does not need to access the memory, it unmaps the memory with [MmUnmapReservedMapping](./nf-wdm-mmunmapreservedmapping.md). The caller can map and unmap the memory buffer as needed, and must unmap it prior to freeing the mapping range with [MmFreeMappingAddress](./nf-wdm-mmfreemappingaddress.md).

Note that the *MappingAddress* parameter specifies the beginning of the range of memory previously reserved by the caller, not the beginning of the memory subrange to be mapped. The caller specifies the starting address and length of the buffer when it allocates the MDL with [IoAllocateMdl](./nf-wdm-ioallocatemdl.md). The buffer must fit inside the reserved memory range, but it can be a strict subset.

The routine uses the *CacheType* parameter only if the pages that are described by the MDL do not already have a cache type associated with them. However, in nearly all cases, the pages already have an associated cache type, and this cache type is used by the new mapping. An exception to this rule is for pages that are allocated by [MmAllocatePagesForMdl](./nf-wdm-mmallocatepagesformdl.md), which do not have a specific cache type associated with them. For such pages, the *CacheType* parameter determines the cache type of the mapping.

## -see-also

[IoAllocateMdl](./nf-wdm-ioallocatemdl.md)

[MEMORY_CACHING_TYPE](./ne-wdm-_memory_caching_type.md)

[MmAllocateMappingAddress](./nf-wdm-mmallocatemappingaddress.md)

[MmAllocatePagesForMdl](./nf-wdm-mmallocatepagesformdl.md)

[MmAllocatePagesForMdlEx](./nf-wdm-mmallocatepagesformdlex.md)

[MmFreeMappingAddress](./nf-wdm-mmfreemappingaddress.md)

[MmProbeAndLockPages](./nf-wdm-mmprobeandlockpages.md)

[MmUnmapReservedMapping](./nf-wdm-mmunmapreservedmapping.md)
