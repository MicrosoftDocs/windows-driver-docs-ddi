---
UID: NS:d3dumddi._DXVAHDDDI_COLOR
title: _DXVAHDDDI_COLOR (d3dumddi.h)
description: The DXVAHDDDI_COLOR union contains information that specifies color with either a YCbCr or RGB color structure.
old-location: display\dxvahdddi_color.htm
tech.root: display
ms.assetid: ac1a2fae-29f1-4143-9d43-b10db300de03
ms.date: 05/10/2018
ms.keywords: DXVA2_Structs_21418f8b-824c-4505-b52a-92437c3ff508.xml, DXVAHDDDI_COLOR, DXVAHDDDI_COLOR union [Display Devices], _DXVAHDDDI_COLOR, d3dumddi/DXVAHDDDI_COLOR, display.dxvahdddi_color
ms.topic: struct
req.header: d3dumddi.h
req.include-header: D3dumddi.h
req.target-type: Windows
req.target-min-winverclnt: DXVAHDDDI_COLOR is supported beginning with the Windows 7 operating system.
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
- DXVAHDDDI_COLOR
product:
- Windows
targetos: Windows
req.typenames: DXVAHDDDI_COLOR
---

# _DXVAHDDDI_COLOR structure


## -description


The DXVAHDDDI_COLOR union contains information that specifies color with either a YCbCr or RGB color structure.  


## -struct-fields




### -field RGB

[in] A <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3dumddi/ns-d3dumddi-_dxvahdddi_color_rgba">DXVAHDDDI_COLOR_RGBA</a> structure that describes color in RGB terms. 


### -field YCbCr

[in] A <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3dumddi/ns-d3dumddi-_dxvahdddi_color_ycbcra">DXVAHDDDI_COLOR_YCbCrA</a> structure that describes color in a YCbCr terms. 


## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3dumddi/ns-d3dumddi-_dxvahdddi_color_rgba">DXVAHDDDI_COLOR_RGBA</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3dumddi/ns-d3dumddi-_dxvahdddi_color_ycbcra">DXVAHDDDI_COLOR_YCbCrA</a>
 

 

