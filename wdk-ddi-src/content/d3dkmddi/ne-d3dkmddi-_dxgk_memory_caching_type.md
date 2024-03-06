---
UID: NE:d3dkmddi._DXGK_MEMORY_CACHING_TYPE
title: DXGK_MEMORY_CACHING_TYPE (d3dkmddi.h)
description: DXGK_MEMORY_CACHING_TYPE describes the memory caching types during allocation.
ms.date: 07/22/2021
keywords: ["DXGK_MEMORY_CACHING_TYPE enumeration"]
ms.keywords: _DXGK_MEMORY_CACHING_TYPE, DXGK_MEMORY_CACHING_TYPE,
req.header: d3dkmddi.h
req.include-header: 
req.target-type: 
req.target-min-winverclnt: Windows 10, version 1803
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: 
req.max-support: 
req.typenames: DXGK_MEMORY_CACHING_TYPE
targetos: Windows
tech.root: display
f1_keywords:
 - _DXGK_MEMORY_CACHING_TYPE
 - d3dkmddi/_DXGK_MEMORY_CACHING_TYPE
 - DXGK_MEMORY_CACHING_TYPE
 - d3dkmddi/DXGK_MEMORY_CACHING_TYPE
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - d3dkmddi.h
api_name:
 - _DXGK_MEMORY_CACHING_TYPE
 - DXGK_MEMORY_CACHING_TYPE
---

# DXGK_MEMORY_CACHING_TYPE enumeration

## -description

**DXGK_MEMORY_CACHING_TYPE** describes the memory caching types during allocation.

## -enum-fields

### -field DXGK_MEMORY_CACHING_TYPE_NON_CACHED

The memory is not cached.

### -field DXGK_MEMORY_CACHING_TYPE_CACHED

The memory is cached.

### -field DXGK_MEMORY_CACHING_TYPE_WRITE_COMBINED

The memory caching type is write combined.

## -remarks

See [IOMMU-based GPU isolation](/windows-hardware/drivers/display/iommu-based-gpu-isolation) for more information.

## -see-also

[**DXGKARGCB_ALLOCATECONTIGUOUSMEMORY**](./ns-d3dkmddi-_dxgkargcb_allocatecontiguousmemory.md)