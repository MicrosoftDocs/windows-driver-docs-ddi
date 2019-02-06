---
UID: NS:d3dkmddi._DXGK_MULTIPLANE_OVERLAY_VSYNC_INFO2
title: _DXGK_MULTIPLANE_OVERLAY_VSYNC_INFO2 (d3dkmddi.h)
description: Used by new drivers to report per-plane flip completion after a VSYNC.
old-location: display\dxgk_multiplane_overlay_vsync_info2.htm
ms.assetid: CC1371C5-1BAB-458C-BC7F-9844B2BBEA3A
ms.date: 05/10/2018
ms.keywords: DXGK_MULTIPLANE_OVERLAY_VSYNC_INFO2, DXGK_MULTIPLANE_OVERLAY_VSYNC_INFO2 structure [Display Devices], _DXGK_MULTIPLANE_OVERLAY_VSYNC_INFO2, d3dkmddi/DXGK_MULTIPLANE_OVERLAY_VSYNC_INFO2, display.dxgk_multiplane_overlay_vsync_info2
ms.topic: struct
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	d3dkmddi.h
api_name:
-	DXGK_MULTIPLANE_OVERLAY_VSYNC_INFO2
product:
- Windows
targetos: Windows
tech.root: display
req.typenames: DXGK_MULTIPLANE_OVERLAY_VSYNC_INFO2
---

# _DXGK_MULTIPLANE_OVERLAY_VSYNC_INFO2 structure


## -description


Used by new drivers to report per-plane flip completion after a VSYNC.


## -struct-fields




### -field LayerIndex

The zero-based index of the overlay plane to display. The top plane (in the z-direction) has index zero. The planes' index values must be sequential from top to bottom.  


### -field PresentId

The 64 bit PresentId specified in the SetVidPnSourceAddressWithMultiPlaneOverlay3() DDI call.


### -field Flags

Flag to indicate whether the scheduler should call DXGKDDI_POSTMULTIPLANEOVERLAYPRESENT for this plane

