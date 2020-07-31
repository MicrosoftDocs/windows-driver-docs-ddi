---
UID: NS:d3dkmddi._DXGK_MULTIPLANE_OVERLAY_PLANE2
title: _DXGK_MULTIPLANE_OVERLAY_PLANE2 (d3dkmddi.h)
description: DXGK_MULTIPLANE_OVERLAY_PLANE2 is used with the DxgkDdiSetVidPnSourceAddressWithMultiPlaneOverlay2 function to specify an overlay plane to display.
old-location: display\dxgk_multiplane_overlay_plane2.htm
ms.assetid: 31A1EAFB-FA48-432D-963E-EA907B43F08A
ms.date: 05/10/2018
keywords: ["_DXGK_MULTIPLANE_OVERLAY_PLANE2 structure"]
ms.keywords: DXGK_MULTIPLANE_OVERLAY_PLANE2, DXGK_MULTIPLANE_OVERLAY_PLANE2 structure [Display Devices], _DXGK_MULTIPLANE_OVERLAY_PLANE2, d3dkmddi/DXGK_MULTIPLANE_OVERLAY_PLANE2, display.dxgk_multiplane_overlay_plane2
f1_keywords:
 - "d3dkmddi/DXGK_MULTIPLANE_OVERLAY_PLANE2"
 - "DXGK_MULTIPLANE_OVERLAY_PLANE2"
req.header: d3dkmddi.h
req.include-header: D3dkmddi.h
req.target-type: Windows
req.target-min-winverclnt: Windows 10
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
topic_type:
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- d3dkmddi.h
api_name:
- DXGK_MULTIPLANE_OVERLAY_PLANE2
targetos: Windows
tech.root: display
req.typenames: DXGK_MULTIPLANE_OVERLAY_PLANE2
---

# _DXGK_MULTIPLANE_OVERLAY_PLANE2 structure


## -description


<b>DXGK_MULTIPLANE_OVERLAY_PLANE2</b> is used with the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dkmddi/nc-d3dkmddi-dxgkddi_setvidpnsourceaddresswithmultiplaneoverlay2">DxgkDdiSetVidPnSourceAddressWithMultiPlaneOverlay2</a> function to specify an overlay plane to display.


## -struct-fields




### -field LayerIndex

The zero-based index of the overlay plane to display. The top plane (in the z-direction) has index zero. The planes' index values must be sequential from top to bottom.


### -field Enabled

Indicates whether the overlay plane specified by <b>LayerIndex</b> is enabled for display.


### -field AllocationSegment

The identifier of a segment that data is read from.


### -field AllocationAddress

A <b>PHYSICAL_ADDRESS</b> data type (which is defined as <b>LARGE_INTEGER</b>) that indicates the physical address within the segment that <b>AllocationSegment</b> specifies, where the data is read.


### -field hAllocation

A handle to the allocation to be displayed on the overlay plane.


### -field PlaneAttributes

A structure of type <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dkmddi/ns-d3dkmddi-_dxgk_multiplane_overlay_attributes2">DXGK_MULTIPLANE_OVERLAY_ATTRIBUTES2</a> that specifies overlay plane attributes.


## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dkmddi/ns-d3dkmddi-_dxgk_multiplane_overlay_attributes2">DXGK_MULTIPLANE_OVERLAY_ATTRIBUTES2</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dkmddi/nc-d3dkmddi-dxgkddi_setvidpnsourceaddresswithmultiplaneoverlay2">DxgkDdiSetVidPnSourceAddressWithMultiPlaneOverlay2</a>
 

 

