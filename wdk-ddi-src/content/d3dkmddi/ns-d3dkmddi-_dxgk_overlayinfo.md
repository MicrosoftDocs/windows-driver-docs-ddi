---
UID: NS:d3dkmddi._DXGK_OVERLAYINFO
title: _DXGK_OVERLAYINFO (d3dkmddi.h)
description: The DXGK_OVERLAYINFO structure describes parameters that are required to create or modify an overlay.
old-location: display\dxgk_overlayinfo.htm
ms.assetid: 7c2a7484-452f-4801-b650-3d8221740892
ms.date: 05/10/2018
keywords: ["DXGK_OVERLAYINFO structure"]
ms.keywords: DXGK_OVERLAYINFO, DXGK_OVERLAYINFO structure [Display Devices], DmStructs_232178f2-9a25-40aa-8604-0414128c1a91.xml, _DXGK_OVERLAYINFO, d3dkmddi/DXGK_OVERLAYINFO, display.dxgk_overlayinfo
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
req.typenames: DXGK_OVERLAYINFO
f1_keywords:
 - _DXGK_OVERLAYINFO
 - d3dkmddi/_DXGK_OVERLAYINFO
 - DXGK_OVERLAYINFO
 - d3dkmddi/DXGK_OVERLAYINFO
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - d3dkmddi.h
api_name:
 - DXGK_OVERLAYINFO
---

# _DXGK_OVERLAYINFO structure


## -description

The DXGK_OVERLAYINFO structure describes parameters that are required to create or modify an overlay.

## -struct-fields

### -field hAllocation

[in] A handle to the allocation to be displayed on the overlay.

### -field PhysicalAddress

[in] The physical address, within the segment that <b>SegmentId</b> specifies, of the allocation to be displayed.

### -field SegmentId

[in] The identifier of a segment in which the allocation is currently paged-in.

### -field DstRect

[in] A <a href="/windows/win32/api/windef/ns-windef-rect">RECT</a> structure that contains the overlay destination rectangle, in device coordinates.

### -field SrcRect

[in] A RECT structure that contains the overlay source rectangle, in device coordinates.

### -field pPrivateDriverData

[in] A pointer to a block of private data that is passed from the user-mode display driver to the display miniport driver.

### -field PrivateDriverDataSize

[in] The size, in bytes, of the block of private data that <b>pPrivateDriverData</b> points to.

## -see-also

<a href="/windows-hardware/drivers/ddi/d3dkmddi/ns-d3dkmddi-_dxgkarg_createoverlay">DXGKARG_CREATEOVERLAY</a>



<a href="/windows-hardware/drivers/ddi/d3dkmddi/ns-d3dkmddi-_dxgkarg_updateoverlay">DXGKARG_UPDATEOVERLAY</a>



<a href="/windows-hardware/drivers/ddi/d3dkmddi/nc-d3dkmddi-dxgkddi_createoverlay">DxgkDdiCreateOverlay</a>



<a href="/windows-hardware/drivers/ddi/d3dkmddi/nc-d3dkmddi-dxgkddi_updateoverlay">DxgkDdiUpdateOverlay</a>



<a href="/windows/win32/api/windef/ns-windef-rect">RECT</a>