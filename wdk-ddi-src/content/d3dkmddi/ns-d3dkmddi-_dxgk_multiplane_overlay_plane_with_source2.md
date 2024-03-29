---
UID: NS:d3dkmddi._DXGK_MULTIPLANE_OVERLAY_PLANE_WITH_SOURCE2
title: _DXGK_MULTIPLANE_OVERLAY_PLANE_WITH_SOURCE2 (d3dkmddi.h)
description: DXGK_MULTIPLANE_OVERLAY_PLANE_WITH_SOURCE2 is used by the DxgkDdiCheckMultiPlaneOverlaySupport3 function to check support for a multi-plane overlay configuration.
old-location: display\dxgk_multiplane_overlay_plane_with_source2.htm
ms.date: 05/10/2018
keywords: ["DXGK_MULTIPLANE_OVERLAY_PLANE_WITH_SOURCE2 structure"]
ms.keywords: DXGK_MULTIPLANE_OVERLAY_PLANE_WITH_SOURCE2, DXGK_MULTIPLANE_OVERLAY_PLANE_WITH_SOURCE2 structure [Display Devices], _DXGK_MULTIPLANE_OVERLAY_PLANE_WITH_SOURCE2, d3dkmddi/DXGK_MULTIPLANE_OVERLAY_PLANE_WITH_SOURCE2, display.dxgk_multiplane_overlay_plane_with_source2
req.header: d3dkmddi.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: 
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
req.typenames: DXGK_MULTIPLANE_OVERLAY_PLANE_WITH_SOURCE2
f1_keywords:
 - _DXGK_MULTIPLANE_OVERLAY_PLANE_WITH_SOURCE2
 - d3dkmddi/_DXGK_MULTIPLANE_OVERLAY_PLANE_WITH_SOURCE2
 - DXGK_MULTIPLANE_OVERLAY_PLANE_WITH_SOURCE2
 - d3dkmddi/DXGK_MULTIPLANE_OVERLAY_PLANE_WITH_SOURCE2
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - d3dkmddi.h
api_name:
 - _DXGK_MULTIPLANE_OVERLAY_PLANE_WITH_SOURCE2
 - DXGK_MULTIPLANE_OVERLAY_PLANE_WITH_SOURCE2
---

# _DXGK_MULTIPLANE_OVERLAY_PLANE_WITH_SOURCE2 structure


## -description

Used in a call to the <i>DxgkDdiCheckMultiPlaneOverlaySupport3</i> function to check details on hardware support for multi-plane overlays.

## -struct-fields

### -field hAllocation

A handle to the allocation.

### -field VidPnSourceId

The zero-based video present network (VidPN) source identification number of the input for which the support levels are queried.

### -field LayerIndex

The zero based index indicating the Z order of the overlay plane.

### -field PlaneAttributes

A [DXGK_MULTIPLANE_OVERLAY_ATTRIBUTES3](ns-d3dkmddi-_dxgk_multiplane_overlay_attributes3.md) structure that specifies overlay plane attributes.

