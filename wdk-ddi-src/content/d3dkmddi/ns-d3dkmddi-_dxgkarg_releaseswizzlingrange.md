---
UID: NS:d3dkmddi._DXGKARG_RELEASESWIZZLINGRANGE
title: _DXGKARG_RELEASESWIZZLINGRANGE (d3dkmddi.h)
description: The DXGKARG_RELEASESWIZZLINGRANGE structure describes parameters for releasing a swizzling range.
old-location: display\dxgkarg_releaseswizzlingrange.htm
ms.date: 05/10/2018
keywords: ["DXGKARG_RELEASESWIZZLINGRANGE structure"]
ms.keywords: DXGKARG_RELEASESWIZZLINGRANGE, DXGKARG_RELEASESWIZZLINGRANGE structure [Display Devices], DmStructs_7ed7a86e-7376-47a8-8198-9c991005fd0a.xml, _DXGKARG_RELEASESWIZZLINGRANGE, d3dkmddi/DXGKARG_RELEASESWIZZLINGRANGE, display.dxgkarg_releaseswizzlingrange
req.header: d3dkmddi.h
req.include-header: D3dkmddi.h
req.target-type: Windows
req.target-min-winverclnt: Available in Windows Vista and later versions of the Windows operating systems.
req.target-min-winversvr: 
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
req.typenames: DXGKARG_RELEASESWIZZLINGRANGE
f1_keywords:
 - _DXGKARG_RELEASESWIZZLINGRANGE
 - d3dkmddi/_DXGKARG_RELEASESWIZZLINGRANGE
 - DXGKARG_RELEASESWIZZLINGRANGE
 - d3dkmddi/DXGKARG_RELEASESWIZZLINGRANGE
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - d3dkmddi.h
api_name:
 - _DXGKARG_RELEASESWIZZLINGRANGE
 - DXGKARG_RELEASESWIZZLINGRANGE
---

# _DXGKARG_RELEASESWIZZLINGRANGE structure


## -description

The DXGKARG_RELEASESWIZZLINGRANGE structure describes parameters for releasing a swizzling range.

## -struct-fields

### -field hAllocation

[in] A handle to the allocation that the display miniport driver assigns and that is returned through the driver's <a href="/windows-hardware/drivers/ddi/d3dkmddi/nc-d3dkmddi-dxgkddi_createallocation">DxgkDdiCreateAllocation</a> function.

### -field PrivateDriverData

[in] The 32 bits of private data that the user-mode display driver sent when the display miniport driver's <a href="/windows-hardware/drivers/ddi/d3dkmddi/nc-d3dkmddi-dxgkddi_acquireswizzlingrange">DxgkDdiAcquireSwizzlingRange</a> function was called to acquire the swizzling range.

### -field RangeId

[in] The zero-based identifier of the swizzling range that the <a href="/windows-hardware/drivers/ddi/d3dkmddi/nc-d3dkmddi-dxgkddi_releaseswizzlingrange">DxgkDdiReleaseSwizzlingRange</a> function releases.

## -see-also

<a href="/windows-hardware/drivers/ddi/d3dkmddi/nc-d3dkmddi-dxgkddi_acquireswizzlingrange">DxgkDdiAcquireSwizzlingRange</a>



<a href="/windows-hardware/drivers/ddi/d3dkmddi/nc-d3dkmddi-dxgkddi_createallocation">DxgkDdiCreateAllocation</a>



<a href="/windows-hardware/drivers/ddi/d3dkmddi/nc-d3dkmddi-dxgkddi_releaseswizzlingrange">DxgkDdiReleaseSwizzlingRange</a>

