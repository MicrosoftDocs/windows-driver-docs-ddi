---
UID: NS:d3dkmddi._DXGKARGCB_UNPINFRAMEBUFFERFORSAVE
title: DXGKARGCB_UNPINFRAMEBUFFERFORSAVE (d3dkmddi.h)
description: The DXGKARGCB_UNPINFRAMEBUFFERFORSAVE structure contains the arguments used by the DXGKCB_UNPINFRAMEBUFFERFORSAVE callback function to release the mapping that was set by DXGKCB_PINFRAMEBUFFERFORSAVE.
ms.date: 07/22/2021
keywords: ["DXGKARGCB_UNPINFRAMEBUFFERFORSAVE structure"]
ms.keywords: _DXGKARGCB_UNPINFRAMEBUFFERFORSAVE, DXGKARGCB_UNPINFRAMEBUFFERFORSAVE,
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
req.typenames: DXGKARGCB_UNPINFRAMEBUFFERFORSAVE
targetos: Windows
tech.root: display
f1_keywords:
 - _DXGKARGCB_UNPINFRAMEBUFFERFORSAVE
 - d3dkmddi/_DXGKARGCB_UNPINFRAMEBUFFERFORSAVE
 - DXGKARGCB_UNPINFRAMEBUFFERFORSAVE
 - d3dkmddi/DXGKARGCB_UNPINFRAMEBUFFERFORSAVE
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - d3dkmddi.h
api_name:
 - _DXGKARGCB_UNPINFRAMEBUFFERFORSAVE
 - DXGKARGCB_UNPINFRAMEBUFFERFORSAVE
product:
 - Windows
---

# DXGKARGCB_UNPINFRAMEBUFFERFORSAVE structure

## -description

The **DXGKARGCB_UNPINFRAMEBUFFERFORSAVE** structure contains the arguments used by the [**DXGKCB_UNPINFRAMEBUFFERFORSAVE**](nc-d3dkmddi-dxgkcb_unpinframebufferforsave.md) callback function to release the mapping that was set by [**DXGKCB_PINFRAMEBUFFERFORSAVE**](nc-d3dkmddi-dxgkcb_pinframebufferforsave.md).

## -struct-fields

### -field PhysicalAdapterIndex

[in] The index of the physical adapter.

## -remarks

See [IOMMU-based GPU isolation](/windows-hardware/drivers/display/iommu-based-gpu-isolation) for more information.

## -see-also

[**DXGKCB_UNPINFRAMEBUFFERFORSAVE**](nc-d3dkmddi-dxgkcb_unpinframebufferforsave.md)

[**DXGKCB_PINFRAMEBUFFERFORSAVE**](nc-d3dkmddi-dxgkcb_pinframebufferforsave.md)

[**DXGKARGCB_PINFRAMEBUFFERFORSAVE**](ns-d3dkmddi-_dxgkargcb_pinframebufferforsave.md)
