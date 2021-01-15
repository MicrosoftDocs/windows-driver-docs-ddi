---
UID: NS:d3dkmddi._DXGK_CREATECONTEXTALLOCATIONFLAGS
title: _DXGK_CREATECONTEXTALLOCATIONFLAGS (d3dkmddi.h)
description: Specifies the properties of the context to be allocated.
old-location: display\dxgk_createcontextallocationflags.htm
ms.date: 05/10/2018
keywords: ["DXGK_CREATECONTEXTALLOCATIONFLAGS structure"]
ms.keywords: DXGK_CREATECONTEXTALLOCATIONFLAGS, DXGK_CREATECONTEXTALLOCATIONFLAGS structure [Display Devices], _DXGK_CREATECONTEXTALLOCATIONFLAGS, d3dkmddi/DXGK_CREATECONTEXTALLOCATIONFLAGS, display.dxgk_createcontextallocationflags
req.header: d3dkmddi.h
req.include-header: D3dkmddi.h
req.target-type: Windows
req.target-min-winverclnt: Windows 8
req.target-min-winversvr: Windows Server 2012
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
req.typenames: DXGK_CREATECONTEXTALLOCATIONFLAGS
f1_keywords:
 - _DXGK_CREATECONTEXTALLOCATIONFLAGS
 - d3dkmddi/_DXGK_CREATECONTEXTALLOCATIONFLAGS
 - DXGK_CREATECONTEXTALLOCATIONFLAGS
 - d3dkmddi/DXGK_CREATECONTEXTALLOCATIONFLAGS
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - D3dkmddi.h
api_name:
 - _DXGK_CREATECONTEXTALLOCATIONFLAGS
 - DXGK_CREATECONTEXTALLOCATIONFLAGS
---

# _DXGK_CREATECONTEXTALLOCATIONFLAGS structure


## -description

Specifies the properties of the context to be allocated.

## -struct-fields

### -field SharedAcrossContexts

[in] A UINT value that specifies the association of the context.

If <b>SharedAcrossContexts</b> is set to one, the allocation is associated with all contexts specified by the <b>hDevice</b> member of the <a href="/windows-hardware/drivers/ddi/d3dkmddi/ns-d3dkmddi-_dxgkargcb_createcontextallocation">DXGKARGCB_CREATECONTEXTALLOCATION</a> structure. The allocated context will be made resident when any context that belongs to <b>hDevice</b> is
                                                            scheduled to run on the GPU.

If <b>SharedAcrossContexts</b> is set to zero, the allocation is associated with the context specified by the <b>hContext</b> member of the <a href="/windows-hardware/drivers/ddi/d3dkmddi/ns-d3dkmddi-_dxgkargcb_createcontextallocation">DXGKARGCB_CREATECONTEXTALLOCATION</a> structure. The allocated context will be made resident when <b>hContext</b> is scheduled to run on the GPU.

### -field MapGpuVirtualAddress

### -field Reserved

[in] This member is reserved and should be set to zero. Setting this member to zero is equivalent to setting the most significant 31 bits (0xFFFFFFFE) to zeros.

### -field Value

[in] A 32-bit value that specifies the context allocation flags.

## -remarks

The display miniport driver allocates GPU contexts or device-specific contexts by calling <a href="/windows-hardware/drivers/ddi/d3dkmddi/nc-d3dkmddi-dxgkcb_createcontextallocation">DxgkCbCreateContextAllocation</a>.

The <b>ContextAllocationFlags</b> member of the <a href="/windows-hardware/drivers/ddi/d3dkmddi/ns-d3dkmddi-_dxgkargcb_createcontextallocation">DXGKARGCB_CREATECONTEXTALLOCATION</a> structure is an <b>DXGK_CREATECONTEXTALLOCATIONFLAGS</b> data type.

## -see-also

<a href="/windows-hardware/drivers/ddi/d3dkmddi/ns-d3dkmddi-_dxgkargcb_createcontextallocation">DXGKARGCB_CREATECONTEXTALLOCATION</a>



<a href="/windows-hardware/drivers/ddi/d3dkmddi/nc-d3dkmddi-dxgkcb_createcontextallocation">DxgkCbCreateContextAllocation</a>

