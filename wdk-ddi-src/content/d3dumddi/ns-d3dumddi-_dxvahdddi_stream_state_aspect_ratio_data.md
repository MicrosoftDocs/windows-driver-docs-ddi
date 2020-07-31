---
UID: NS:d3dumddi._DXVAHDDDI_STREAM_STATE_ASPECT_RATIO_DATA
title: _DXVAHDDDI_STREAM_STATE_ASPECT_RATIO_DATA (d3dumddi.h)
description: The DXVAHDDDI_STREAM_STATE_ASPECT_RATIO_DATA structure describes stream-state data that specifies the pixel aspect ratio.
old-location: display\dxvahdddi_stream_state_aspect_ratio_data.htm
tech.root: display
ms.assetid: 12d33e2d-63d3-4cc8-9b50-5156132b2e72
ms.date: 05/10/2018
keywords: ["_DXVAHDDDI_STREAM_STATE_ASPECT_RATIO_DATA structure"]
ms.keywords: DXVA2_Structs_daab6809-2f81-4892-9f56-c57254047627.xml, DXVAHDDDI_STREAM_STATE_ASPECT_RATIO_DATA, DXVAHDDDI_STREAM_STATE_ASPECT_RATIO_DATA structure [Display Devices], _DXVAHDDDI_STREAM_STATE_ASPECT_RATIO_DATA, d3dumddi/DXVAHDDDI_STREAM_STATE_ASPECT_RATIO_DATA, display.dxvahdddi_stream_state_aspect_ratio_data
f1_keywords:
 - "d3dumddi/DXVAHDDDI_STREAM_STATE_ASPECT_RATIO_DATA"
 - "DXVAHDDDI_STREAM_STATE_ASPECT_RATIO_DATA"
req.header: d3dumddi.h
req.include-header: D3dumddi.h
req.target-type: Windows
req.target-min-winverclnt: DXVAHDDDI_STREAM_STATE_ASPECT_RATIO_DATA is supported beginning with the Windows 7 operating system.
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
- DXVAHDDDI_STREAM_STATE_ASPECT_RATIO_DATA
targetos: Windows
req.typenames: DXVAHDDDI_STREAM_STATE_ASPECT_RATIO_DATA
---

# _DXVAHDDDI_STREAM_STATE_ASPECT_RATIO_DATA structure


## -description


The DXVAHDDDI_STREAM_STATE_ASPECT_RATIO_DATA structure describes stream-state data that specifies the pixel aspect ratio. 


## -struct-fields




### -field Enable

[in] A Boolean value that specifies whether the pixel aspect ratios are available. The default value is <b>FALSE</b>, which indicates that the pixel aspect ratios are not available. 


### -field SourceAspectRatio

[in] A <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dumddi/ns-d3dumddi-_dxvahdddi_rational">DXVAHDDDI_RATIONAL</a> structure that specifies the pixel aspect ratio of the source. The default is (1, 1). 


### -field DestinationAspectRatio

[in] A <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dumddi/ns-d3dumddi-_dxvahdddi_rational">DXVAHDDDI_RATIONAL</a> structure that specifies the pixel aspect ratio of the destination. The default is (1, 1). 


## -remarks



The driver might require the source and destination pixel aspect ratios to achieve the best result. 

The <b>DXVAHDDDI_STREAM_STATE_ASPECT_RATIO</b> stream state is best set along with the <b>DXVAHDDDI_STREAM_STATE_FILTER_ANAMORPHIC_SCALING</b> stream state.

Pixel aspect ratios (0, any value) and (any value, 0) are invalid and causes the driver to return an error. 




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dumddi/ns-d3dumddi-_dxvahdddi_rational">DXVAHDDDI_RATIONAL</a>
 

 

