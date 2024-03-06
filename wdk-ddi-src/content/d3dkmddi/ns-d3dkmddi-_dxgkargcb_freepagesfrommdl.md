---
UID: NS:d3dkmddi._DXGKARGCB_FREEPAGESFROMMDL
title: DXGKARGCB_FREEPAGESFROMMDL (d3dkmddi.h)
description: The DXGKARGCB_FREEPAGESFROMMDL structure contains the arguments used in the DXGKCB_FREEPAGESFROMMDL callback function.
ms.date: 10/13/2021
keywords: ["DXGKARGCB_FREEPAGESFROMMDL structure"]
ms.keywords: _DXGKARGCB_FREEPAGESFROMMDL, DXGKARGCB_FREEPAGESFROMMDL,
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
req.typenames: DXGKARGCB_FREEPAGESFROMMDL
targetos: Windows
tech.root: display
f1_keywords:
 - _DXGKARGCB_FREEPAGESFROMMDL
 - d3dkmddi/_DXGKARGCB_FREEPAGESFROMMDL
 - DXGKARGCB_FREEPAGESFROMMDL
 - d3dkmddi/DXGKARGCB_FREEPAGESFROMMDL
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - d3dkmddi.h
api_name:
 - _DXGKARGCB_FREEPAGESFROMMDL
 - DXGKARGCB_FREEPAGESFROMMDL
---

# DXGKARGCB_FREEPAGESFROMMDL structure

## -description

The **DXGKARGCB_FREEPAGESFROMMDL** structure contains the arguments used in the [**DXGKCB_FREEPAGESFROMMDL**](nc-d3dkmddi-dxgkcb_freepagesfrommdl.md) callback function, to free a memory descriptor list's (MDL) pages that were previously allocated by [**DXGKCB_ALLOCATEPAGESFORMDL**](ns-d3dkmddi-_dxgkargcb_allocatepagesformdl.md).

## -struct-fields

### -field hMemoryHandle [in]

A *Dxgkrnl* tracking handle for the memory allocation.

## -remarks

See [IOMMU-based GPU isolation](/windows-hardware/drivers/display/iommu-based-gpu-isolation) for more information.

## -see-also

[DXGKCB_FREEPAGESFROMMDL](nc-d3dkmddi-dxgkcb_freepagesfrommdl.md)
