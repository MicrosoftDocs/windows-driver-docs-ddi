---
UID: NE:miniport._MEMORY_CACHING_TYPE
title: _MEMORY_CACHING_TYPE (miniport.h)
description: The MEMORY_CACHING_TYPE enumeration type specifies the permitted caching behavior when allocating or mapping memory.
old-location: kernel\memory_caching_type.htm
tech.root: kernel
ms.assetid: 14cde545-e9bb-4b96-ba10-a63595e8a107
ms.date: 04/30/2018
ms.keywords: MEMORY_CACHING_TYPE, MEMORY_CACHING_TYPE enumeration [Kernel-Mode Driver Architecture], MmCached, MmHardwareCoherentCached, MmMaximumCacheType, MmNonCached, MmNonCachedUnordered, MmUSWCCached, MmWriteCombined, _MEMORY_CACHING_TYPE, kernel.memory_caching_type, sysenum_8e18fde8-a812-4d6a-a203-1c87d4d825cf.xml, wdm/MEMORY_CACHING_TYPE, wdm/MmCached, wdm/MmHardwareCoherentCached, wdm/MmMaximumCacheType, wdm/MmNonCached, wdm/MmNonCachedUnordered, wdm/MmUSWCCached, wdm/MmWriteCombined
ms.topic: enum
req.header: miniport.h
req.include-header: Ntddk.h, Wdm.h, Miniport.h, Wudfwdm.h
req.target-type: Windows
req.target-min-winverclnt: Supported in Windows 2000 and later versions of Windows.
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
req.lib: 
req.dll: 
req.irql: 
topic_type:
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- Wdm.h
api_name:
- MEMORY_CACHING_TYPE
product:
- Windows
targetos: Windows
req.typenames: MEMORY_CACHING_TYPE
---

# _MEMORY_CACHING_TYPE enumeration


## -description


The <b>MEMORY_CACHING_TYPE</b> enumeration type specifies the permitted caching behavior when allocating or mapping memory.


## -enum-fields




### -field MmNonCached

The requested memory should not be cached by the processor.


### -field MmCached

The processor should cache the requested memory.


### -field MmWriteCombined

The requested memory should not be cached by the processor, but writes to the memory can be combined by the processor.


### -field MmHardwareCoherentCached

Reserved for system use.


### -field MmNonCachedUnordered

Reserved for system use.


### -field MmUSWCCached

Reserved for system use.


### -field MmMaximumCacheType

Reserved for system use.


### -field MmNotMapped




## -remarks



Processor translation buffers cache virtual to physical address translations. These translation buffers allow many virtual addresses to map a single physical address. However, only one caching behavior is allowed for any given physical address translation. Therefore, if a driver maps two different virtual address ranges to the same physical address, it must ensure that it specifies the same caching behavior for both. Otherwise, the processor behavior is undefined with unpredictable system results.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdm/nf-wdm-mmallocatecontiguousmemoryspecifycache">MmAllocateContiguousMemorySpecifyCache</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdm/nf-wdm-mmfreecontiguousmemoryspecifycache">MmFreeContiguousMemorySpecifyCache</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdm/nf-wdm-mmmapiospace">MmMapIoSpace</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdm/nf-wdm-mmmaplockedpagesspecifycache">MmMapLockedPagesSpecifyCache</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdm/nf-wdm-mmmaplockedpageswithreservedmapping">MmMapLockedPagesWithReservedMapping</a>
 

 

