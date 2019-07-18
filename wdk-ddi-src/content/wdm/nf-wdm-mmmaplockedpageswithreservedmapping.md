---
UID: NF:wdm.MmMapLockedPagesWithReservedMapping
title: MmMapLockedPagesWithReservedMapping function (wdm.h)
description: The MmMapLockedPagesWithReservedMapping routine maps all or part of an address range that was previously reserved by the MmAllocateMappingAddress routine.
old-location: kernel\mmmaplockedpageswithreservedmapping.htm
tech.root: kernel
ms.assetid: 3fc01bc5-05eb-482f-b625-67061d26915a
ms.date: 04/30/2018
ms.keywords: MmMapLockedPagesWithReservedMapping, MmMapLockedPagesWithReservedMapping routine [Kernel-Mode Driver Architecture], k106_32161803-dd44-4a5f-a5c0-da6b1a78982c.xml, kernel.mmmaplockedpageswithreservedmapping, wdm/MmMapLockedPagesWithReservedMapping
ms.topic: function
f1_keywords:
 - "wdm/MmMapLockedPagesWithReservedMapping"
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
req.irql: "<= DISPATCH_LEVEL"
topic_type:
- APIRef
- kbSyntax
api_type:
- DllExport
api_location:
- NtosKrnl.exe
api_name:
- MmMapLockedPagesWithReservedMapping
product:
- Windows
targetos: Windows
req.typenames: 
---

# MmMapLockedPagesWithReservedMapping function


## -description


The <b>MmMapLockedPagesWithReservedMapping</b> routine maps all or part of an address range that was previously reserved by the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdm/nf-wdm-mmallocatemappingaddress">MmAllocateMappingAddress</a> routine. 


## -parameters




### -param MappingAddress [in]

Pointer to the beginning of the reserved virtual memory range. This must be an address previously returned by <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdm/nf-wdm-mmallocatemappingaddress">MmAllocateMappingAddress</a>.


### -param PoolTag [in]

Specifies the pool tag for the reserved memory buffer. This must be identical to the value specified in the <i>PoolTag</i> parameter of the call to <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdm/nf-wdm-mmallocatemappingaddress">MmAllocateMappingAddress</a> that reserved the buffer. 


### -param MemoryDescriptorList [in]

A pointer to the MDL that is to be mapped. This MDL must describe physical pages that are locked down. A locked-down MDL can be built by the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdm/nf-wdm-mmprobeandlockpages">MmProbeAndLockPages</a> or <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdm/nf-wdm-mmallocatepagesformdlex">MmAllocatePagesForMdlEx</a> routine. 


### -param CacheType [in]

Specifies the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdm/ne-wdm-_memory_caching_type">MEMORY_CACHING_TYPE</a> value to use to create the mapping.


## -returns



<b>MmMapLockedPagesWithReservedMapping</b> returns a pointer to the beginning of the mapped memory, or <b>NULL</b> if the system could not map the memory. This routine returns <b>NULL</b> only if there is an error in the function parameters (for example, the driver's mapping address is not large enough to span the supplied MDL). This function is intended to enable drivers to make forward progress even in low-resource scenarios.




## -remarks



The caller can use <b>MmMapLockedPagesWithReservedMapping</b> to map a subrange of the virtual memory range reserved by <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdm/nf-wdm-mmallocatemappingaddress">MmAllocateMappingAddress</a> as follows: 

<ol>
<li>
Use <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdm/nf-wdm-ioallocatemdl">IoAllocateMdl</a> to allocate an MDL. The returned MDL is built using the specified starting address and size of the subrange of the virtual memory range to map. 

</li>
<li>
Use <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdm/nf-wdm-mmprobeandlockpages">MmProbeAndLockPages</a> to lock down the physical pages described by the MDL obtained in step 1.

</li>
<li>
Use <b>MmMapLockedPagesWithReservedMapping</b> to actually map the virtual memory to the physical memory that was locked down in step 2. Note that the virtual address returned by this function does include the byte offset that the MDL specifies. However, the <b>MappedSystemVa</b> field of the MDL that is set by this function does <u>not</u> include the byte offset. 

</li>
</ol>
Once the caller does not need to access the memory, it unmaps the memory with <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdm/nf-wdm-mmunmapreservedmapping">MmUnmapReservedMapping</a>. The caller can map and unmap the memory buffer as needed, and must unmap it prior to freeing the mapping range with <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdm/nf-wdm-mmfreemappingaddress">MmFreeMappingAddress</a>. 

Note that the <i>MappingAddress</i> parameter specifies the beginning of the range of memory previously reserved by the caller, <u>not</u> the beginning of the memory subrange to be mapped. The caller specifies the starting address and length of the buffer when it allocates the MDL with <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdm/nf-wdm-ioallocatemdl">IoAllocateMdl</a>. The buffer must fit inside the reserved memory range, but it can be a strict subset.

The routine uses the <i>CacheType</i> parameter only if the pages that are described by the MDL do not already have a cache type associated with them. However, in nearly all cases, the pages already have an associated cache type, and this cache type is used by the new mapping. An exception to this rule is for pages that are allocated by <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdm/nf-wdm-mmallocatepagesformdl">MmAllocatePagesForMdl</a>, which do not have a specific cache type associated with them. For such pages, the <i>CacheType</i> parameter determines the cache type of the mapping. 




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdm/nf-wdm-ioallocatemdl">IoAllocateMdl</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdm/ne-wdm-_memory_caching_type">MEMORY_CACHING_TYPE</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdm/nf-wdm-mmallocatemappingaddress">MmAllocateMappingAddress</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdm/nf-wdm-mmallocatepagesformdl">MmAllocatePagesForMdl</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdm/nf-wdm-mmallocatepagesformdlex">MmAllocatePagesForMdlEx</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdm/nf-wdm-mmfreemappingaddress">MmFreeMappingAddress</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdm/nf-wdm-mmprobeandlockpages">MmProbeAndLockPages</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdm/nf-wdm-mmunmapreservedmapping">MmUnmapReservedMapping</a>
 

 

