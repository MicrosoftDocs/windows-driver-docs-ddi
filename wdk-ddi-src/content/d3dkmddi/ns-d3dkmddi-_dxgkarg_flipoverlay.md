---
UID: NS:d3dkmddi._DXGKARG_FLIPOVERLAY
title: _DXGKARG_FLIPOVERLAY (d3dkmddi.h)
description: The DXGKARG_FLIPOVERLAY structure describes a new allocation to display for the overlay.
old-location: display\dxgkarg_flipoverlay.htm
ms.assetid: c5396581-e9f2-47eb-bb82-1e54f5def4d0
ms.date: 05/10/2018
keywords: ["DXGKARG_FLIPOVERLAY structure"]
ms.keywords: DXGKARG_FLIPOVERLAY, DXGKARG_FLIPOVERLAY structure [Display Devices], DmStructs_8ff06344-e7f5-44b1-95fc-d3b363428d43.xml, _DXGKARG_FLIPOVERLAY, d3dkmddi/DXGKARG_FLIPOVERLAY, display.dxgkarg_flipoverlay
f1_keywords:
 - "d3dkmddi/DXGKARG_FLIPOVERLAY"
 - "DXGKARG_FLIPOVERLAY"
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
topic_type:
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- d3dkmddi.h
api_name:
- DXGKARG_FLIPOVERLAY
targetos: Windows
tech.root: display
req.typenames: DXGKARG_FLIPOVERLAY
---

# _DXGKARG_FLIPOVERLAY structure


## -description


The DXGKARG_FLIPOVERLAY structure describes a new allocation to display for the overlay. 


## -struct-fields




### -field hSource

[in] A handle to the source allocation to be displayed.


### -field SrcPhysicalAddress

[in] The physical address, within the segment that <b>SrcSegmentId</b> specifies, of the allocation to be displayed.


### -field SrcSegmentId

[in] The identifier of a segment in which the allocation is currently paged.


### -field pPrivateDriverData

[in] A pointer to a block of private data that is passed from the user-mode display driver to the display miniport driver. 


### -field PrivateDriverDataSize

[in] The size, in bytes, of the block of private data that <b>pPrivateDriverData</b> points to.


## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dkmddi/nc-d3dkmddi-dxgkddi_flipoverlay">DxgkDdiFlipOverlay</a>
 

 

