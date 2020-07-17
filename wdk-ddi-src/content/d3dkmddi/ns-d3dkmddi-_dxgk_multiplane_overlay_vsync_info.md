---
UID: NS:d3dkmddi._DXGK_MULTIPLANE_OVERLAY_VSYNC_INFO
title: _DXGK_MULTIPLANE_OVERLAY_VSYNC_INFO (d3dkmddi.h)
description: Specifies an overlay plane to display during a VSync interval.
old-location: display\dxgk_multiplane_overlay_vsync_info.htm
ms.assetid: b3e93b4d-7d0a-4862-a405-2bf7f78244ef
ms.date: 05/10/2018
keywords: ["_DXGK_MULTIPLANE_OVERLAY_VSYNC_INFO structure"]
ms.keywords: DXGK_MULTIPLANE_OVERLAY_VSYNC_INFO, DXGK_MULTIPLANE_OVERLAY_VSYNC_INFO structure [Display Devices], _DXGK_MULTIPLANE_OVERLAY_VSYNC_INFO, d3dkmddi/DXGK_MULTIPLANE_OVERLAY_VSYNC_INFO, display.dxgk_multiplane_overlay_vsync_info
f1_keywords:
 - "d3dkmddi/DXGK_MULTIPLANE_OVERLAY_VSYNC_INFO"
 - "DXGK_MULTIPLANE_OVERLAY_VSYNC_INFO"
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
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- D3dkmddi.h
api_name:
- DXGK_MULTIPLANE_OVERLAY_VSYNC_INFO
product:
- Windows
targetos: Windows
tech.root: display
req.typenames: DXGK_MULTIPLANE_OVERLAY_VSYNC_INFO
---

# _DXGK_MULTIPLANE_OVERLAY_VSYNC_INFO structure


## -description


Specifies an overlay plane to display during a VSync interval.


## -struct-fields




### -field LayerIndex

The zero-based index of the overlay plane to display. The top plane (in the z-direction) has index zero. The planes' index values must be sequential from top to bottom.


### -field Enabled

Indicates if the overlay plane specified by <b>LayerIndex</b> is enabled for display.


### -field PhysicalAddress

[in] A <b>PHYSICAL_ADDRESS</b> data type (which is defined as <b>LARGE_INTEGER</b>) that indicates the physical address within the segment where the data is read.


### -field PlaneAttributes

A structure of type <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dkmddi/ns-d3dkmddi-_dxgk_multiplane_overlay_attributes">DXGK_MULTIPLANE_OVERLAY_ATTRIBUTES</a>  that specifies overlay plane attributes.

