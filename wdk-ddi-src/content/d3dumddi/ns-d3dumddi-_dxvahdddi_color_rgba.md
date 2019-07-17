---
UID: NS:d3dumddi._DXVAHDDDI_COLOR_RGBA
title: _DXVAHDDDI_COLOR_RGBA (d3dumddi.h)
description: The DXVAHDDDI_COLOR_RGBA structure describes color in RGB terms.
old-location: display\dxvahdddi_color_rgba.htm
tech.root: display
ms.assetid: 73779eb1-514e-4103-9af2-0dc0c86cb04e
ms.date: 05/10/2018
ms.keywords: DXVA2_Structs_ecf8ab79-edb1-42c8-b873-39cc1f7a1ef8.xml, DXVAHDDDI_COLOR_RGBA, DXVAHDDDI_COLOR_RGBA structure [Display Devices], _DXVAHDDDI_COLOR_RGBA, d3dumddi/DXVAHDDDI_COLOR_RGBA, display.dxvahdddi_color_rgba
ms.topic: struct
f1_keywords:
 - "d3dumddi/DXVAHDDDI_COLOR_RGBA"
req.header: d3dumddi.h
req.include-header: D3dumddi.h
req.target-type: Windows
req.target-min-winverclnt: DXVAHDDDI_COLOR_RGBA is supported beginning with the Windows 7 operating system.
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
- DXVAHDDDI_COLOR_RGBA
product:
- Windows
targetos: Windows
req.typenames: DXVAHDDDI_COLOR_RGBA
---

# _DXVAHDDDI_COLOR_RGBA structure


## -description


The DXVAHDDDI_COLOR_RGBA structure describes color in RGB terms.  


## -struct-fields




### -field R

[in] A FLOAT value in the 0.0 to 1.0 range that is used to describe the red component of the RGB color. 


### -field G

[in] A FLOAT value in the 0.0 to 1.0 range that is used to describe the green component of the RGB color.


### -field B

[in] A FLOAT value in the 0.0 to 1.0 range that is used to describe the blue component of the RGB color.


### -field A

[in] A FLOAT value in the 0.0 to 1.0 range that is used to describe the alpha component (that is, the transparency level) of the RGB color.


## -remarks



The setting of DXVAHDDDI_COLOR_RGBA for full range RGB black with opaque alpha is (0.0, 0.0, 0.0, 1.0). The setting of DXVAHDDDI_COLOR_RGBA for limited range RGB black with half transparent alpha is (0.0625, 0.0625, 0.0625, 0.5), which is (0, 0, 0, 255) and (16, 16, 16, 128) respectively when 8-bit presentation is used.

R, G, and B values can be out of the [0.0, 1.0] range for wide gamut format (for example, for XR_BIAS, FP16, and FP32 formats).

A DXVAHDDDI_COLOR_YCbCrA structure is specified in the <b>RGB</b> member of the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3dumddi/ns-d3dumddi-_dxvahdddi_color">DXVAHDDDI_COLOR</a> union to specify the color in RGB terms.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3dumddi/ns-d3dumddi-_dxvahdddi_color">DXVAHDDDI_COLOR</a>
 

 

