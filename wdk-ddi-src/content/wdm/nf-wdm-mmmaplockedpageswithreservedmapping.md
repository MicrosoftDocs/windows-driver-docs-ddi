---
UID: NF:wdm.MmMapLockedPagesWithReservedMapping
title: MmMapLockedPagesWithReservedMapping function
author: windows-driver-content
description: The MmMapLockedPagesWithReservedMapping routine maps all or part of an address range that was previously reserved by the MmAllocateMappingAddress routine.
old-location: kernel\mmmaplockedpageswithreservedmapping.htm
old-project: kernel
ms.assetid: 3fc01bc5-05eb-482f-b625-67061d26915a
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: ",  , L, M, MmMapLockedPagesWithReservedMapping, MmMapLockedPagesWithReservedMapping routine [Kernel-Mode Driver Architecture], P, R, W, a, c, d, e, g, h, i, k, k106_32161803-dd44-4a5f-a5c0-da6b1a78982c.xml, kernel.mmmaplockedpageswithreservedmapping, m, n, o, p, r, s, t, v, wdm/MmMapLockedPagesWithReservedMapping"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	DllExport
apilocation:
-	NtosKrnl.exe
apiname:
-	MmMapLockedPagesWithReservedMapping
product: Windows
targetos: Windows
req.typenames: WORK_QUEUE_TYPE
req.product: Windows 10 or later.
---

# MmMapLockedPagesWithReservedMapping function


## -description


The <b>MmMapLockedPagesWithReservedMapping</b> routine maps all or part of an address range that was previously reserved by the <a href="..\wdm\nf-wdm-mmallocatemappingaddress.md">MmAllocateMappingAddress</a> routine. 


## -syntax


````
PVOID MmMapLockedPagesWithReservedMapping(
  _In_ PVOID               MappingAddress,
  _In_ ULONG               PoolTag,
  _In_ PMDLX               MemoryDescriptorList,
  _In_ MEMORY_CACHING_TYPE CacheType
);
````


## -parameters




### -param MappingAddress [in]

Pointer to the beginning of the reserved virtual memory range. This must be an address previously returned by <a href="..\wdm\nf-wdm-mmallocatemappingaddress.md">MmAllocateMappingAddress</a>.


### -param PoolTag [in]

Specifies the pool tag for the reserved memory buffer. This must be identical to the value specified in the <i>PoolTag</i> parameter of the call to <a href="..\wdm\nf-wdm-mmallocatemappingaddress.md">MmAllocateMappingAddress</a> that reserved the buffer. 


### -param MemoryDescriptorList [in]

A pointer to the MDL that is to be mapped. This MDL must describe physical pages that are locked down. A locked-down MDL can be built by the <a href="..\wdm\nf-wdm-mmprobeandlockpages.md">MmProbeAndLockPages</a> or <a href="..\wdm\nf-wdm-mmallocatepagesformdlex.md">MmAllocatePagesForMdlEx</a> routine. 


### -param CacheType [in]

Specifies the <a href="..\wdm\ne-wdm-_memory_caching_type.md">MEMORY_CACHING_TYPE</a> value to use to create the mapping.


## -returns



<b>MmMapLockedPagesWithReservedMapping</b> returns a pointer to the beginning of the mapped memory, or <b>NULL</b> if the system could not map the memory. This routine returns <b>NULL</b> only if there is an error in the function parameters (for example, the driver's mapping address is not large enough to span the supplied MDL). This function is intended to enable drivers to make forward progress even in low-resource scenarios.




## -remarks



The caller can use <b>MmMapLockedPagesWithReservedMapping</b> to map a subrange of the virtual memory range reserved by <a href="..\wdm\nf-wdm-mmallocatemappingaddress.md">MmAllocateMappingAddress</a> as follows: 

<ol>
<li>
Use <a href="..\wdm\nf-wdm-ioallocatemdl.md">IoAllocateMdl</a> to allocate an MDL. The returned MDL is built using the specified starting address and size of the subrange of the virtual memory range to map. 

</li>
<li>
Use <a href="..\wdm\nf-wdm-mmprobeandlockpages.md">MmProbeAndLockPages</a> to lock down the physical pages described by the MDL obtained in step 1.

</li>
<li>
Use <b>MmMapLockedPagesWithReservedMapping</b> to actually map the virtual memory to the physical memory that was locked down in step 2. Note that the virtual address returned by this function does include the byte offset that the MDL specifies. However, the <b>MappedSystemVa</b> field of the MDL that is set by this function does <u>not</u> include the byte offset. 

</li>
</ol>
Once the caller does not need to access the memory, it unmaps the memory with <a href="..\wdm\nf-wdm-mmunmapreservedmapping.md">MmUnmapReservedMapping</a>. The caller can map and unmap the memory buffer as needed, and must unmap it prior to freeing the mapping range with <a href="..\wdm\nf-wdm-mmfreemappingaddress.md">MmFreeMappingAddress</a>. 

Note that the <i>MappingAddress</i> parameter specifies the beginning of the range of memory previously reserved by the caller, <u>not</u> the beginning of the memory subrange to be mapped. The caller specifies the starting address and length of the buffer when it allocates the MDL with <a href="..\wdm\nf-wdm-ioallocatemdl.md">IoAllocateMdl</a>. The buffer must fit inside the reserved memory range, but it can be a strict subset.

The routine uses the <i>CacheType</i> parameter only if the pages that are described by the MDL do not already have a cache type associated with them. However, in nearly all cases, the pages already have an associated cache type, and this cache type is used by the new mapping. An exception to this rule is for pages that are allocated by <a href="..\wdm\nf-wdm-mmallocatepagesformdl.md">MmAllocatePagesForMdl</a>, which do not have a specific cache type associated with them. For such pages, the <i>CacheType</i> parameter determines the cache type of the mapping. 




## -see-also

<a href="..\wdm\nf-wdm-ioallocatemdl.md">IoAllocateMdl</a>



<a href="..\wdm\nf-wdm-mmallocatepagesformdlex.md">MmAllocatePagesForMdlEx</a>



<a href="..\wdm\ne-wdm-_memory_caching_type.md">MEMORY_CACHING_TYPE</a>



<a href="..\wdm\nf-wdm-mmallocatemappingaddress.md">MmAllocateMappingAddress</a>



<a href="..\wdm\nf-wdm-mmallocatepagesformdl.md">MmAllocatePagesForMdl</a>



<a href="..\wdm\nf-wdm-mmunmapreservedmapping.md">MmUnmapReservedMapping</a>



<a href="..\wdm\nf-wdm-mmfreemappingaddress.md">MmFreeMappingAddress</a>



<a href="..\wdm\nf-wdm-mmprobeandlockpages.md">MmProbeAndLockPages</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20MmMapLockedPagesWithReservedMapping routine%20 RELEASE:%20(2/16/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

