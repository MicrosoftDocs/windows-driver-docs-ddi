---
UID: NS:d3dkmddi._DXGKARGCB_ALLOCATEPAGESFORMDL
title: DXGKARGCB_ALLOCATEPAGESFORMDL (d3dkmddi.h)
description: The DXGKARGCB_ALLOCATEPAGESFORMDL structure contains the arguments used in the DXGKCB_ALLOCATEPAGESFORMDL callback function, to allocate pages for a memory descriptor list (MDL).
ms.date: 10/13/2021
keywords: ["DXGKARGCB_ALLOCATEPAGESFORMDL structure"]
ms.keywords: _DXGKARGCB_ALLOCATEPAGESFORMDL, DXGKARGCB_ALLOCATEPAGESFORMDL, *INOUT_PDXGKARGCB_ALLOCATEPAGESFORMDL
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
req.typenames: DXGKARGCB_ALLOCATEPAGESFORMDL
targetos: Windows
tech.root: display
f1_keywords:
 - _DXGKARGCB_ALLOCATEPAGESFORMDL
 - d3dkmddi/_DXGKARGCB_ALLOCATEPAGESFORMDL
 - DXGKARGCB_ALLOCATEPAGESFORMDL
 - d3dkmddi/DXGKARGCB_ALLOCATEPAGESFORMDL
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - d3dkmddi.h
api_name:
 - _DXGKARGCB_ALLOCATEPAGESFORMDL
 - DXGKARGCB_ALLOCATEPAGESFORMDL
product:
 - Windows
---

# DXGKARGCB_ALLOCATEPAGESFORMDL structure

## -description

The **DXGKARGCB_ALLOCATEPAGESFORMDL** structure contains the arguments used in the [**DXGKCB_ALLOCATEPAGESFORMDL**](nc-d3dkmddi-dxgkcb_allocatepagesformdl.md) callback function, to allocate pages for a memory descriptor list (MDL).

## -struct-fields

### -field LowAddress

[in] Specifies the physical address of the start of the first address range from which the allocated pages can come.

### -field HighAddress

[in] Specifies the physical address of the end of the first address range from which the allocated pages can come.

### -field SkipBytes

[in] Specifies the number of bytes to skip from the start of the previous address range from which the allocated pages can come. SkipBytes must be an integer multiple of the virtual memory page size, in bytes.

### -field TotalBytes

[in] Specifies the total number of bytes to allocate for the MDL.

### -field CacheType

[in] Indicates the type of caching that is allowed for the requested memory.

### -field Flags

[in] Specifies the flags for this operation. For more information, see [MmAllocatePagesForMdlEx function](../wdm/nf-wdm-mmallocatepagesformdlex.md).

### -field hMemoryHandle

[out] A *Dxgkrnl* tracking handle for the allocation. This value should be passed to the corresponding [**DGXKCB_FREEPAGESFROMMDL**](nc-d3dkmddi-dxgkcb_freepagesfrommdl.md) callback function.

### -field pMdl

[out] An MDL of non-paged memory guaranteed to be mapped to the IOMMU for its lifetime.

## -remarks

See [IOMMU-based GPU isolation](/windows-hardware/drivers/display/iommu-based-gpu-isolation) for more information.

## -see-also

[**DXGKCB_ALLOCATEPAGESFORMDL**](nc-d3dkmddi-dxgkcb_allocatepagesformdl.md)
