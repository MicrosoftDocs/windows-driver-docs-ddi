---
UID: NS:d3dkmddi._DXGK_CHECK_MULTIPLANE_OVERLAY_SUPPORT_PLANE
title: _DXGK_CHECK_MULTIPLANE_OVERLAY_SUPPORT_PLANE (d3dkmddi.h)
description: Specifies the support attributes that the hardware provides for multiplane overlays.
old-location: display\dxgk_check_multiplane_overlay_support_plane.htm
ms.date: 05/10/2018
keywords: ["DXGK_CHECK_MULTIPLANE_OVERLAY_SUPPORT_PLANE structure"]
ms.keywords: DXGK_CHECK_MULTIPLANE_OVERLAY_SUPPORT_PLANE, DXGK_CHECK_MULTIPLANE_OVERLAY_SUPPORT_PLANE structure [Display Devices], _DXGK_CHECK_MULTIPLANE_OVERLAY_SUPPORT_PLANE, d3dkmddi/DXGK_CHECK_MULTIPLANE_OVERLAY_SUPPORT_PLANE, display.dxgk_check_multiplane_overlay_support_plane
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
req.typenames: DXGK_CHECK_MULTIPLANE_OVERLAY_SUPPORT_PLANE
f1_keywords:
 - _DXGK_CHECK_MULTIPLANE_OVERLAY_SUPPORT_PLANE
 - d3dkmddi/_DXGK_CHECK_MULTIPLANE_OVERLAY_SUPPORT_PLANE
 - DXGK_CHECK_MULTIPLANE_OVERLAY_SUPPORT_PLANE
 - d3dkmddi/DXGK_CHECK_MULTIPLANE_OVERLAY_SUPPORT_PLANE
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - D3dkmddi.h
api_name:
 - DXGK_CHECK_MULTIPLANE_OVERLAY_SUPPORT_PLANE
---

# _DXGK_CHECK_MULTIPLANE_OVERLAY_SUPPORT_PLANE structure


## -description

Specifies the support attributes that the hardware provides for multiplane overlays.

## -struct-fields

### -field hAllocation

[out] A handle to the allocation. The display miniport driver must set this member to a value that it can use to refer to its private tracking structure for the allocation.

### -field VidPnSourceId

[in] The zero-based video present network (VidPN) source identification number of the input for which the support levels are queried.

### -field PlaneAttributes

A <a href="/windows-hardware/drivers/ddi/d3dkmddi/ns-d3dkmddi-_dxgk_multiplane_overlay_attributes">DXGK_MULTIPLANE_OVERLAY_ATTRIBUTES</a> structure that specifies overlay plane attributes.

## -see-also

<a href="/windows-hardware/drivers/ddi/d3dkmddi/ns-d3dkmddi-_dxgk_multiplane_overlay_attributes">DXGK_MULTIPLANE_OVERLAY_ATTRIBUTES</a>
