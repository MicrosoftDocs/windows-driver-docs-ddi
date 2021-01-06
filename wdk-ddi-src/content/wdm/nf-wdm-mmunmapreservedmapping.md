---
UID: NF:wdm.MmUnmapReservedMapping
title: MmUnmapReservedMapping function (wdm.h)
description: The MmUnmapReservedMapping routine unmaps a memory buffer that was mapped by the MmMapLockedPagesWithReservedMapping routine.
old-location: kernel\mmunmapreservedmapping.htm
tech.root: kernel
ms.date: 04/30/2018
keywords: ["MmUnmapReservedMapping function"]
ms.keywords: MmUnmapReservedMapping, MmUnmapReservedMapping routine [Kernel-Mode Driver Architecture], k106_48bc7719-e11c-4c70-a976-c7fbecbff464.xml, kernel.mmunmapreservedmapping, wdm/MmUnmapReservedMapping
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
req.irql: <=DISPATCH_LEVEL
targetos: Windows
req.typenames: 
f1_keywords:
 - MmUnmapReservedMapping
 - wdm/MmUnmapReservedMapping
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - DllExport
api_location:
 - NtosKrnl.exe
api_name:
 - MmUnmapReservedMapping
---

# MmUnmapReservedMapping function


## -description

The <b>MmUnmapReservedMapping</b> routine unmaps a memory buffer that was mapped by the <a href="/windows-hardware/drivers/ddi/wdm/nf-wdm-mmmaplockedpageswithreservedmapping">MmMapLockedPagesWithReservedMapping</a> routine.

## -parameters

### -param BaseAddress 

[in]
Pointer to the beginning of the reserved virtual memory range. This must be an address returned by <a href="/windows-hardware/drivers/ddi/wdm/nf-wdm-mmmaplockedpageswithreservedmapping">MmMapLockedPagesWithReservedMapping</a>.

### -param PoolTag 

[in]
Specifies the pool tag for the reserved memory buffer. This must be identical to the value specified in the <i>PoolTag</i> parameter of the call to <a href="/windows-hardware/drivers/ddi/wdm/nf-wdm-mmallocatemappingaddress">MmAllocateMappingAddress</a> that initially reserved the buffer.

### -param MemoryDescriptorList 

[in]
Pointer to the MDL that describes the physical memory mapping.

## -see-also

<a href="/windows-hardware/drivers/ddi/wdm/nf-wdm-mmallocatemappingaddress">MmAllocateMappingAddress</a>



<a href="/windows-hardware/drivers/ddi/wdm/nf-wdm-mmfreemappingaddress">MmFreeMappingAddress</a>



<a href="/windows-hardware/drivers/ddi/wdm/nf-wdm-mmmaplockedpageswithreservedmapping">MmMapLockedPagesWithReservedMapping</a>
