---
UID: NS:d3dkmddi._DXGKARGCB_FREECONTIGUOUSMEMORY
title: DXGKARGCB_FREECONTIGUOUSMEMORY (d3dkmddi.h)
description: The DXGKARGCB_FREECONTIGUOUSMEMORY structure contains the arguments used in the DXGKCB_FREECONTIGUOUSMEMORY callback function, to free the contiguous memory.
ms.date: 10/13/2021
keywords: ["DXGKARGCB_FREECONTIGUOUSMEMORY structure"]
ms.keywords: _DXGKARGCB_FREECONTIGUOUSMEMORY, DXGKARGCB_FREECONTIGUOUSMEMORY,
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
req.typenames: DXGKARGCB_FREECONTIGUOUSMEMORY
targetos: Windows
tech.root: display
f1_keywords:
 - _DXGKARGCB_FREECONTIGUOUSMEMORY
 - d3dkmddi/_DXGKARGCB_FREECONTIGUOUSMEMORY
 - DXGKARGCB_FREECONTIGUOUSMEMORY
 - d3dkmddi/DXGKARGCB_FREECONTIGUOUSMEMORY
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - d3dkmddi.h
api_name:
 - _DXGKARGCB_FREECONTIGUOUSMEMORY
 - DXGKARGCB_FREECONTIGUOUSMEMORY
product:
 - Windows
---

# DXGKARGCB_FREECONTIGUOUSMEMORY structure

## -description

The **DXGKARGCB_FREECONTIGUOUSMEMORY** structure contains the arguments used in the [**DXGKCB_FREECONTIGUOUSMEMORY**](nc-d3dkmddi-dxgkcb_freecontiguousmemory.md) callback function, to free the contiguous memory.

## -struct-fields

### -field hMemoryHandle

[in] A *Dxgkrnl* tracking handle for the memory allocation. *Dxgkrnl* returns this handle from [**DXGKCB_ALLOCATECONTIGUOUSMEMORY**](nc-d3dkmddi-dxgkcb_allocatecontiguousmemory.md)

## -remarks

See [IOMMU-based GPU isolation](/windows-hardware/drivers/display/iommu-based-gpu-isolation) for more information.

## -see-also

[DXGKCB_FREECONTIGUOUSMEMORY](nc-d3dkmddi-dxgkcb_freecontiguousmemory.md)
