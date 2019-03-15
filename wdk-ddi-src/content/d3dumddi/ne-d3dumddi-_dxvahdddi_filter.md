---
UID: NE:d3dumddi._DXVAHDDDI_FILTER
title: _DXVAHDDDI_FILTER (d3dumddi.h)
description: The DXVAHDDDI_FILTER enumeration contains values that identify the filter range, which the driver should retrieve when the driver's GetCaps function is called with the D3DDDICAPS_DXVAHD_GETVPFILTERRANGE value set.
old-location: display\dxvahdddi_filter.htm
tech.root: display
ms.assetid: dbf65c28-b4f2-4930-8d01-050c45f87bb4
ms.date: 05/10/2018
ms.keywords: DXVA2_Structs_730202a4-96bd-4779-b952-d493295f06ad.xml, DXVAHDDDI_FILTER, DXVAHDDDI_FILTER enumeration [Display Devices], DXVAHDDDI_FILTER_ANAMORPHIC_SCALING, DXVAHDDDI_FILTER_BRIGHTNESS, DXVAHDDDI_FILTER_CONTRAST, DXVAHDDDI_FILTER_EDGE_ENHANCEMENT, DXVAHDDDI_FILTER_HUE, DXVAHDDDI_FILTER_NOISE_REDUCTION, DXVAHDDDI_FILTER_SATURATION, _DXVAHDDDI_FILTER, d3dumddi/DXVAHDDDI_FILTER, d3dumddi/DXVAHDDDI_FILTER_ANAMORPHIC_SCALING, d3dumddi/DXVAHDDDI_FILTER_BRIGHTNESS, d3dumddi/DXVAHDDDI_FILTER_CONTRAST, d3dumddi/DXVAHDDDI_FILTER_EDGE_ENHANCEMENT, d3dumddi/DXVAHDDDI_FILTER_HUE, d3dumddi/DXVAHDDDI_FILTER_NOISE_REDUCTION, d3dumddi/DXVAHDDDI_FILTER_SATURATION, display.dxvahdddi_filter
ms.topic: enum
req.header: d3dumddi.h
req.include-header: D3dumddi.h
req.target-type: Windows
req.target-min-winverclnt: DXVAHDDDI_FILTER is supported beginning with the Windows 7 operating system.
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
- d3dumddi.h
api_name:
- DXVAHDDDI_FILTER
product:
- Windows
targetos: Windows
req.typenames: DXVAHDDDI_FILTER
---

# _DXVAHDDDI_FILTER enumeration


## -description


The DXVAHDDDI_FILTER enumeration contains values that identify the filter range, which the driver should retrieve when the driver's <a href="https://msdn.microsoft.com/cf6c61ce-7b53-46d0-b3ff-ed5b2b964c65">GetCaps</a> function is called with the D3DDDICAPS_DXVAHD_GETVPFILTERRANGE value set. 


## -enum-fields




### -field DXVAHDDDI_FILTER_BRIGHTNESS

A value that specifies the filter range of the brightness ProcAmp. 


### -field DXVAHDDDI_FILTER_CONTRAST

A value that specifies the filter range of the contrast ProcAmp. 


### -field DXVAHDDDI_FILTER_HUE

A value that specifies the filter range of the hue ProcAmp. 


### -field DXVAHDDDI_FILTER_SATURATION

A value that specifies the filter range of the saturation ProcAmp. 


### -field DXVAHDDDI_FILTER_NOISE_REDUCTION

A value that specifies the filter range of the noise reduction filter. 


### -field DXVAHDDDI_FILTER_EDGE_ENHANCEMENT

A value that specifies the filter range of the edge enhancement filter. 


### -field DXVAHDDDI_FILTER_ANAMORPHIC_SCALING

A value that specifies that the filter range of anamorphic scaling. 


## -see-also




<a href="https://msdn.microsoft.com/cf6c61ce-7b53-46d0-b3ff-ed5b2b964c65">GetCaps</a>
 

 

