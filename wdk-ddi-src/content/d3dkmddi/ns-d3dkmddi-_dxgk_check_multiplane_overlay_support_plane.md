---
UID: NS:d3dkmddi._DXGK_CHECK_MULTIPLANE_OVERLAY_SUPPORT_PLANE
title: _DXGK_CHECK_MULTIPLANE_OVERLAY_SUPPORT_PLANE (d3dkmddi.h)
description: Specifies the support attributes that the hardware provides for multiplane overlays.
old-location: display\dxgk_check_multiplane_overlay_support_plane.htm
ms.assetid: 28CC4BE1-D4C1-4D22-885B-D50BE5AD6EE6
ms.date: 05/10/2018
ms.keywords: DXGK_CHECK_MULTIPLANE_OVERLAY_SUPPORT_PLANE, DXGK_CHECK_MULTIPLANE_OVERLAY_SUPPORT_PLANE structure [Display Devices], _DXGK_CHECK_MULTIPLANE_OVERLAY_SUPPORT_PLANE, d3dkmddi/DXGK_CHECK_MULTIPLANE_OVERLAY_SUPPORT_PLANE, display.dxgk_check_multiplane_overlay_support_plane
ms.topic: struct
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	D3dkmddi.h
api_name:
-	DXGK_CHECK_MULTIPLANE_OVERLAY_SUPPORT_PLANE
product:
- Windows
targetos: Windows
tech.root: display
req.typenames: DXGK_CHECK_MULTIPLANE_OVERLAY_SUPPORT_PLANE
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

A <a href="https://msdn.microsoft.com/library/windows/hardware/hh780301">DXGK_MULTIPLANE_OVERLAY_ATTRIBUTES</a> structure that specifies overlay plane attributes.


## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/hh780301">DXGK_MULTIPLANE_OVERLAY_ATTRIBUTES</a>
 

 

