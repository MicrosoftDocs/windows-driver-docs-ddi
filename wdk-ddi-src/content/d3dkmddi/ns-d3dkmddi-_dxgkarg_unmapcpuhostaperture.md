---
UID: NS:d3dkmddi._DXGKARG_UNMAPCPUHOSTAPERTURE
title: _DXGKARG_UNMAPCPUHOSTAPERTURE (d3dkmddi.h)
description: The DXGKARG_UNMAPCPUHOSTAPERTURE structure is used to unmap a previously mapped range of the CPU host aperture.
old-location: display\dxgkarg_unmapcpuhostaperture.htm
ms.assetid: 22482590-B0F7-4F35-95D5-9B352810047D
ms.date: 05/10/2018
keywords: ["_DXGKARG_UNMAPCPUHOSTAPERTURE structure"]
ms.keywords: DXGKARG_UNMAPCPUHOSTAPERTURE, DXGKARG_UNMAPCPUHOSTAPERTURE structure [Display Devices], _DXGKARG_UNMAPCPUHOSTAPERTURE, d3dkmddi/DXGKARG_UNMAPCPUHOSTAPERTURE, display.dxgkarg_unmapcpuhostaperture
f1_keywords:
 - "d3dkmddi/DXGKARG_UNMAPCPUHOSTAPERTURE"
 - "DXGKARG_UNMAPCPUHOSTAPERTURE"
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
- DXGKARG_UNMAPCPUHOSTAPERTURE
product:
- Windows
targetos: Windows
tech.root: display
req.typenames: DXGKARG_UNMAPCPUHOSTAPERTURE
---

# _DXGKARG_UNMAPCPUHOSTAPERTURE structure


## -description


The <b>DXGKARG_UNMAPCPUHOSTAPERTURE</b> structure is used to unmap a previously mapped range of the CPU host aperture.


## -struct-fields




### -field NumberOfPages

Specifies the number of pages being unmapped.


### -field pCpuHostAperturePages

Array of CPU host aperture pages to unmap. This is an array of page indices from the start of the CPU host aperture physical address.


### -field SegmentId

The driver segment identifier (starting from 1) of the segment for which the CPU host aperture is unmapped.


### -field PhysicalAdapterIndex

The zero-based physical adapter index in a linked display adapter link.

<div class="alert"><b>Note</b>  The page size is equal to the segment page size.</div>
<div> </div>

## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dkmddi/nc-d3dkmddi-dxgkddi_unmapcpuhostaperture">DxgkDdiUnmapCpuHostAperture</a>
 

 

