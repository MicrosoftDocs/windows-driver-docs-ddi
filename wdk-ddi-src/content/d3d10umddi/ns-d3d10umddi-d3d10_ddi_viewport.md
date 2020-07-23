---
UID: NS:d3d10umddi.D3D10_DDI_VIEWPORT
title: D3D10_DDI_VIEWPORT (d3d10umddi.h)
description: The D3D10_DDI_VIEWPORT structure describes a viewport.
old-location: display\d3d10_ddi_viewport.htm
ms.assetid: 5b2025ce-e0dd-434d-b92b-16ecaf24808f
ms.date: 05/10/2018
keywords: ["D3D10_DDI_VIEWPORT structure"]
ms.keywords: D3D10_DDI_VIEWPORT, D3D10_DDI_VIEWPORT structure [Display Devices], UMDisplayDriver_Dx10param_Structs_820ac08a-01a2-4e47-8573-aedf3c3769e1.xml, d3d10umddi/D3D10_DDI_VIEWPORT, display.d3d10_ddi_viewport
f1_keywords:
 - "d3d10umddi/D3D10_DDI_VIEWPORT"
 - "D3D10_DDI_VIEWPORT"
req.header: d3d10umddi.h
req.include-header: D3d10umddi.h
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
- d3d10umddi.h
api_name:
- D3D10_DDI_VIEWPORT
targetos: Windows
tech.root: display
req.typenames: D3D10_DDI_VIEWPORT
---

# D3D10_DDI_VIEWPORT structure


## -description


The D3D10_DDI_VIEWPORT structure describes a viewport.


## -struct-fields




### -field TopLeftX

[in] A single-precision float vector for the top-left x-coordinate of the viewport.


### -field TopLeftY

[in] A single-precision float vector for the top-left y-coordinate of the viewport.


### -field Width


      [in] A single-precision float vector for the width of the viewport.
     


### -field Height

[in] A single-precision float vector for the height of the viewport.


### -field MinDepth

[in] A single-precision float vector for the minimum depth of the viewport.


### -field MaxDepth

[in] A single-precision float vector for the maximum depth of the viewport.


## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d10ddi_setviewports">SetViewports</a>
 

 

