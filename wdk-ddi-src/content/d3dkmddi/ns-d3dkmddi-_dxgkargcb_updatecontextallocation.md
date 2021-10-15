---
UID: NS:d3dkmddi._DXGKARGCB_UPDATECONTEXTALLOCATION
title: DXGKARGCB_UPDATECONTEXTALLOCATION (d3dkmddi.h)
description: DXGKARGCB_UPDATECONTEXTALLOCATION contains the data used to call DxgkCbUpdateContextAllocation.
old-location: display\dxgkargcb_updatecontextallocation.htm
ms.date: 10/13/2021
keywords: ["DXGKARGCB_UPDATECONTEXTALLOCATION structure"]
ms.keywords: DXGKARGCB_UPDATECONTEXTALLOCATION, DXGKARGCB_UPDATECONTEXTALLOCATION structure [Display Devices], _DXGKARGCB_UPDATECONTEXTALLOCATION, d3dkmddi/DXGKARGCB_UPDATECONTEXTALLOCATION, display.dxgkargcb_updatecontextallocation
req.header: d3dkmddi.h
req.include-header: D3dkmddi.h
req.target-type: Windows
req.target-min-winverclnt: Windows 10 (WDDM 2.0)
req.target-min-winversvr: Windows Server 2016
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
targetos: Windows
tech.root: display
req.typenames: DXGKARGCB_UPDATECONTEXTALLOCATION
f1_keywords:
 - _DXGKARGCB_UPDATECONTEXTALLOCATION
 - d3dkmddi/_DXGKARGCB_UPDATECONTEXTALLOCATION
 - DXGKARGCB_UPDATECONTEXTALLOCATION
 - d3dkmddi/DXGKARGCB_UPDATECONTEXTALLOCATION
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - d3dkmddi.h
api_name:
 - _DXGKARGCB_UPDATECONTEXTALLOCATION
 - DXGKARGCB_UPDATECONTEXTALLOCATION
---

# DXGKARGCB_UPDATECONTEXTALLOCATION structure

## -description

**DXGKARGCB_UPDATECONTEXTALLOCATION** contains the arguments used by the [**DXGKCB_UPDATECONTEXTALLOCATION**](nc-d3dkmddi-dxgkcb_updatecontextallocation.md) callback function, to update the contents of a context allocation.

## -struct-fields

### -field hAllocation

[in] Handle to the context allocation being updated. The allocation defines a physical adapter in a linked display adapter link.

### -field pPrivateDriverData

[in] Pointer to a private driver data buffer to be passed to the [**DXGKCB_UPDATECONTEXTALLOCATION**](nc-d3dkmddi-dxgkcb_updatecontextallocation.md) paging operation.

### -field PrivateDriverDataSize

[in] The size of the driver private data, in bytes.

## -see-also

[**DXGKCB_UPDATECONTEXTALLOCATION**](nc-d3dkmddi-dxgkcb_updatecontextallocation.md)
