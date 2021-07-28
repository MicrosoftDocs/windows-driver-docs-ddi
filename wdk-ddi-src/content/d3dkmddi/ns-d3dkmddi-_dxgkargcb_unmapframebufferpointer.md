---
UID: NS:d3dkmddi._DXGKARGCB_UNMAPFRAMEBUFFERPOINTER
title: DXGKARGCB_UNMAPFRAMEBUFFERPOINTER (d3dkmddi.h)
description: The DXGKARGCB_UNMAPFRAMEBUFFERPOINTER structure contains the arguments used by the DXGKCB_UNMAPFRAMEBUFFERPOINTER callback function to release a mapping.
ms.date: 07/22/2021
keywords: ["DXGKARGCB_UNMAPFRAMEBUFFERPOINTER structure"]
ms.keywords: _DXGKARGCB_UNMAPFRAMEBUFFERPOINTER, DXGKARGCB_UNMAPFRAMEBUFFERPOINTER,
req.header: d3dkmddi.h
req.include-header: 
req.target-type: 
req.target-min-winverclnt: Windows 10, version 1803
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.lib: 
req.dll: 
req.ddi-compliance: 
req.unicode-ansi: 
req.max-support: 
req.typenames: DXGKARGCB_UNMAPFRAMEBUFFERPOINTER
targetos: Windows
tech.root: display
f1_keywords:
 - _DXGKARGCB_UNMAPFRAMEBUFFERPOINTER
 - d3dkmddi/_DXGKARGCB_UNMAPFRAMEBUFFERPOINTER
 - DXGKARGCB_UNMAPFRAMEBUFFERPOINTER
 - d3dkmddi/DXGKARGCB_UNMAPFRAMEBUFFERPOINTER
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - d3dkmddi.h
api_name:
 - _DXGKARGCB_UNMAPFRAMEBUFFERPOINTER
 - DXGKARGCB_UNMAPFRAMEBUFFERPOINTER
product:
 - Windows
---

# DXGKARGCB_UNMAPFRAMEBUFFERPOINTER structure

## -description

The **DXGKARGCB_UNMAPFRAMEBUFFERPOINTER** structure contains the arguments used by the [**DXGKCB_UNMAPFRAMEBUFFERPOINTER**](nc-d3dkmddi-dxgkcb_unmapframebufferpointer.md) callback function to release a mapping.

## -struct-fields

### -field PhysicalAdapterIndex

[in] The index of the physical adapter.

### -field pBaseAddress

[in] A CPU accessible base address pointer to the mapped subregion of the section object.

## -remarks

See [IOMMU-based GPU isolation](/windows-hardware/drivers/display/iommu-based-gpu-isolation) for more information.

## -see-also

[**DXGKCB_UNMAPFRAMEBUFFERPOINTER**](nc-d3dkmddi-dxgkcb_unmapframebufferpointer.md)
