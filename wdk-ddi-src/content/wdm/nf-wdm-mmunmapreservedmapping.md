---
UID: NF:wdm.MmUnmapReservedMapping
title: MmUnmapReservedMapping function (wdm.h)
description: The MmUnmapReservedMapping routine unmaps a memory buffer that was mapped by the MmMapLockedPagesWithReservedMapping routine.
old-location: kernel\mmunmapreservedmapping.htm
tech.root: kernel
ms.assetid: 5f2bb0ef-af54-48e7-a2f5-8c8877bedb4a
ms.date: 04/30/2018
ms.keywords: MmUnmapReservedMapping, MmUnmapReservedMapping routine [Kernel-Mode Driver Architecture], k106_48bc7719-e11c-4c70-a976-c7fbecbff464.xml, kernel.mmunmapreservedmapping, wdm/MmUnmapReservedMapping
ms.topic: function
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h
req.target-type: Universal
req.target-min-winverclnt: Available in Windows XP and later versions of Windows.
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
req.irql: "<=DISPATCH_LEVEL"
topic_type:
- APIRef
- kbSyntax
api_type:
- DllExport
api_location:
- NtosKrnl.exe
api_name:
- MmUnmapReservedMapping
product:
- Windows
targetos: Windows
req.typenames: 
---

# MmUnmapReservedMapping function


## -description


The <b>MmUnmapReservedMapping</b> routine unmaps a memory buffer that was mapped by the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdm/nf-wdm-mmmaplockedpageswithreservedmapping">MmMapLockedPagesWithReservedMapping</a> routine. 


## -parameters




### -param BaseAddress [in]

Pointer to the beginning of the reserved virtual memory range. This must be an address returned by <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdm/nf-wdm-mmmaplockedpageswithreservedmapping">MmMapLockedPagesWithReservedMapping</a>. 


### -param PoolTag [in]

Specifies the pool tag for the reserved memory buffer. This must be identical to the value specified in the <i>PoolTag</i> parameter of the call to <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdm/nf-wdm-mmallocatemappingaddress">MmAllocateMappingAddress</a> that initially reserved the buffer.


### -param MemoryDescriptorList [in]

Pointer to the MDL that describes the physical memory mapping.


## -returns



None




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdm/nf-wdm-mmallocatemappingaddress">MmAllocateMappingAddress</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdm/nf-wdm-mmfreemappingaddress">MmFreeMappingAddress</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdm/nf-wdm-mmmaplockedpageswithreservedmapping">MmMapLockedPagesWithReservedMapping</a>
 

 

