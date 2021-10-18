---
UID: NS:d3dkmddi._DXGKARGCB_ALLOCATECONTIGUOUSMEMORY
title: DXGKARGCB_ALLOCATECONTIGUOUSMEMORY (d3dkmddi.h)
description: The DXGKARGCB_ALLOCATECONTIGUOUSMEMORY structure contains the arguments used in the DXGKCB_ALLOCATECONTIGUOUSMEMORY callback function, to allocate contiguous memory.
ms.date: 10/13/2021
keywords: ["DXGKARGCB_ALLOCATECONTIGUOUSMEMORY structure"]
ms.keywords: _DXGKARGCB_ALLOCATECONTIGUOUSMEMORY, DXGKARGCB_ALLOCATECONTIGUOUSMEMORY, *INOUT_PDXGKARGCB_ALLOCATECONTIGUOUSMEMORY
req.header: d3dkmddi.h
req.include-header: 
req.target-type: 
req.target-min-winverclnt: Windows 10, version 1803 (WDDM 2.4)
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.lib: 
req.dll: 
req.ddi-compliance: 
req.unicode-ansi: 
req.max-support: 
req.typenames: DXGKARGCB_ALLOCATECONTIGUOUSMEMORY
targetos: Windows
tech.root: display
f1_keywords:
 - _DXGKARGCB_ALLOCATECONTIGUOUSMEMORY
 - d3dkmddi/_DXGKARGCB_ALLOCATECONTIGUOUSMEMORY
 - DXGKARGCB_ALLOCATECONTIGUOUSMEMORY
 - d3dkmddi/DXGKARGCB_ALLOCATECONTIGUOUSMEMORY
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - d3dkmddi.h
api_name:
 - _DXGKARGCB_ALLOCATECONTIGUOUSMEMORY
 - DXGKARGCB_ALLOCATECONTIGUOUSMEMORY
product:
 - Windows
---

# DXGKARGCB_ALLOCATECONTIGUOUSMEMORY structure

## -description

The **DXGKARGCB_ALLOCATECONTIGUOUSMEMORY** structure contains the arguments used in the [**DXGKCB_ALLOCATECONTIGUOUSMEMORY**](nc-d3dkmddi-dxgkcb_allocatecontiguousmemory.md) callback function, to allocate contiguous memory.

## -struct-fields

### -field NumberOfBytes

[in] The size, in bytes, of the block of contiguous memory to allocate.

### -field LowestAcceptableAddress

[in] The lowest valid physical address the caller can use. For example, if a device can address only locations above the first 8 megabytes of the processor's physical memory address range, the driver for this device should set LowestAcceptableAddress to 0x0000000000800000.

### -field HighestAcceptableAddress

[in] The highest valid physical address the caller can use. For example, if a device can address only locations in the first 16 megabytes of the processor's physical memory address range, the driver for this device should set HighestAcceptableAddress to 0x0000000000FFFFFF.

### -field BoundaryAddressMultiple

[in] The physical address multiple that the allocated buffer must not cross. A physical address multiple must always be a power of two. This parameter is optional and can be specified as zero to indicate that the device has no special memory boundary restrictions.

### -field CacheType

[in] A [**DXGK_MEMORY_CACHING_TYPE**](ne-d3dkmddi-_dxgk_memory_caching_type.md) value that specifies the cache type of the pages to allocate.

### -field hMemoryHandle

[out] A *Dxgkrnl* tracking handle for the allocation. This value should be passed to the corresponding [**DGXKCB_FREECONTIGUOUSMEMORY**](nc-d3dkmddi-dxgkcb_freecontiguousmemory.md) callback function.

### -field pMemory

[out] A contiguous chunk of non-paged physical memory guaranteed to be mapped to the IOMMU for its lifetime.

## -remarks

See [IOMMU-based GPU isolation](/windows-hardware/drivers/display/iommu-based-gpu-isolation) for more information.

## -see-also

[**DXGKCB_ALLOCATECONTIGUOUSMEMORY**](nc-d3dkmddi-dxgkcb_allocatecontiguousmemory.md)
