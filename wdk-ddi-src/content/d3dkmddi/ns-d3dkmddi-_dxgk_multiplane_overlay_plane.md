---
UID: NS:d3dkmddi._DXGK_MULTIPLANE_OVERLAY_PLANE
title: _DXGK_MULTIPLANE_OVERLAY_PLANE (d3dkmddi.h)
description: Specifies an overlay plane to display in a call to the DxgkDdiSetVidPnSourceAddressWithMultiPlaneOverlay function.
old-location: display\dxgk_multiplane_overlay_plane.htm
ms.date: 05/10/2018
keywords: ["DXGK_MULTIPLANE_OVERLAY_PLANE structure"]
ms.keywords: DXGK_MULTIPLANE_OVERLAY_PLANE, DXGK_MULTIPLANE_OVERLAY_PLANE structure [Display Devices], _DXGK_MULTIPLANE_OVERLAY_PLANE, d3dkmddi/DXGK_MULTIPLANE_OVERLAY_PLANE, display.dxgk_multiplane_overlay_plane
req.header: d3dkmddi.h
req.include-header: D3dkmddi.h
req.target-type: Windows
req.target-min-winverclnt: Windows 8.1
req.target-min-winversvr: Windows Server 2012 R2
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
req.typenames: DXGK_MULTIPLANE_OVERLAY_PLANE
f1_keywords:
 - _DXGK_MULTIPLANE_OVERLAY_PLANE
 - d3dkmddi/_DXGK_MULTIPLANE_OVERLAY_PLANE
 - DXGK_MULTIPLANE_OVERLAY_PLANE
 - d3dkmddi/DXGK_MULTIPLANE_OVERLAY_PLANE
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - D3dkmddi.h
api_name:
 - _DXGK_MULTIPLANE_OVERLAY_PLANE
 - DXGK_MULTIPLANE_OVERLAY_PLANE
---

# _DXGK_MULTIPLANE_OVERLAY_PLANE structure

> [!NOTE] This structure has been replaced by [DXGK_MULTIPLANE_OVERLAY_PLANE3](ns-d3dkmddi-_dxgk_multiplane_overlay_plane3.md).


## -description

Specifies an overlay plane to display in a call to the <a href="/windows-hardware/drivers/ddi/d3dkmddi/nc-d3dkmddi-dxgkddi_setvidpnsourceaddresswithmultiplaneoverlay">DxgkDdiSetVidPnSourceAddressWithMultiPlaneOverlay</a> function.

## -struct-fields

### -field LayerIndex

The zero-based index of the overlay plane to display. The top plane (in the z-direction) has index zero. The planes' index values must be sequential from top to bottom.

### -field Enabled

Indicates whether the overlay plane specified by <b>LayerIndex</b> is enabled for display.

If <b>FALSE</b>, the display miniport driver should disable the specified overlay plane.

If a plane was enabled during a previous call to <a href="/windows-hardware/drivers/ddi/d3dkmddi/nc-d3dkmddi-dxgkddi_setvidpnsourceaddresswithmultiplaneoverlay">DxgkDdiSetVidPnSourceAddressWithMultiPlaneOverlay</a>, the driver should continue to display the plane without flipping it.

### -field AllocationSegment

[in] The identifier of a segment that data is read from.

### -field AllocationAddress

[in] A <b>PHYSICAL_ADDRESS</b> data type (which is defined as <b>LARGE_INTEGER</b>) that indicates the physical address, within the segment that <b>AllocationSegment</b> specifies, where the data is read.

### -field hAllocation

A handle to the allocation to be displayed on the overlay plane.

### -field PlaneAttributes

A structure of type <a href="/windows-hardware/drivers/ddi/d3dkmddi/ns-d3dkmddi-_dxgk_multiplane_overlay_attributes">DXGK_MULTIPLANE_OVERLAY_ATTRIBUTES</a>  that specifies overlay plane attributes.

## -see-also

<a href="/windows-hardware/drivers/ddi/d3dkmddi/ns-d3dkmddi-_dxgk_allocationinfo">DXGK_ALLOCATIONINFO</a>



<a href="/windows-hardware/drivers/ddi/d3dkmddi/ns-d3dkmddi-_dxgk_multiplane_overlay_attributes">DXGK_MULTIPLANE_OVERLAY_ATTRIBUTES</a>



<a href="/windows-hardware/drivers/ddi/d3dkmddi/nc-d3dkmddi-dxgkddi_createallocation">DxgkDdiCreateAllocation</a>



<a href="/windows-hardware/drivers/ddi/d3dkmddi/nc-d3dkmddi-dxgkddi_setvidpnsourceaddresswithmultiplaneoverlay">DxgkDdiSetVidPnSourceAddressWithMultiPlaneOverlay</a>

