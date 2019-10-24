---
UID: NS:d3dkmddi._DXGKARGCB_ALLOCATEPAGESFORMDL
title: _DXGKARGCB_ALLOCATEPAGESFORMDL (d3dkmddi.h)
description: Arguments used in the DXGKCB_ALLOCATEPAGESFORMDL callback function, to allocate pages for MDL.
ms.assetid: c41ff98e-5704-441d-b73f-1fad90895555
ms.date: 10/19/2018
ms.topic: struct
f1_keywords:
 - "d3dkmddi/_DXGKARGCB_ALLOCATEPAGESFORMDL"
ms.keywords: _DXGKARGCB_ALLOCATEPAGESFORMDL, DXGKARGCB_ALLOCATEPAGESFORMDL, *INOUT_PDXGKARGCB_ALLOCATEPAGESFORMDL
req.header: d3dkmddi.h
req.include-header:
req.target-type:
req.target-min-winverclnt:
req.target-min-winversvr:
req.kmdf-ver:
req.umdf-ver:
req.lib:
req.dll:
req.ddi-compliance:
req.unicode-ansi:
req.max-support:
req.typenames: DXGKARGCB_ALLOCATEPAGESFORMDL
topic_type:
- apiref
api_type:
- HeaderDef
api_location:
- d3dkmddi.h
api_name:
- _DXGKARGCB_ALLOCATEPAGESFORMDL
product: 
- Windows
targetos: Windows
tech.root: display
---

# _DXGKARGCB_ALLOCATEPAGESFORMDL structure

## -description

Arguments used in the [DXGKCB_ALLOCATEPAGESFORMDL](nc-d3dkmddi-dxgkcb_allocatepagesformdl.md) callback function, to allocate pages for MDL.

## -struct-fields

### -field LowAddress

Specifies the physical address of the start of the first address range from which the allocated pages can come.

### -field HighAddress

Specifies the physical address of the end of the first address range from which the allocated pages can come.

### -field SkipBytes

Specifies the number of bytes to skip from the start of the previous address range from which the allocated pages can come. SkipBytes must be an integer multiple of the virtual memory page size, in bytes.

### -field TotalBytes

Specifies the total number of bytes to allocate for the MDL.

### -field CacheType

Indicates the type of caching that is allowed for the requested memory.

### -field Flags

Specifies flags for this operation. For more information, see [MmAllocatePagesForMdlEx function](https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-mmallocatepagesformdlex).

### -field hMemoryHandle

A Dxgkrnl tracking handle for the allocation. This value should be passed to the corresponding [DGXKCB_FREEPAGESFROMMDL](nc-d3dkmddi-dxgkcb_freepagesfrommdl.md) callback function.

### -field pMdl

An MDL of non-paged memory guaranteed to be mapped to the IoMmu for its lifetime.

## -remarks

## -see-also
