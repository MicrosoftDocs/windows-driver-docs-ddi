---
UID: NS:d3dumddi._DXVAHDDDI_COLOR_YCbCrA
title: "_DXVAHDDDI_COLOR_YCbCrA"
author: windows-driver-content
description: The DXVAHDDDI_COLOR_YCbCrA structure describes color in YCbCr terms.
old-location: display\dxvahdddi_color_ycbcra.htm
tech.root: display
ms.assetid: e2a624e9-599e-4325-820b-945b3e649323
ms.author: windowsdriverdev
ms.date: 5/10/2018
ms.keywords: DXVA2_Structs_28a4ec5c-f8e6-414b-ac91-846e3b0fdbf8.xml, DXVAHDDDI_COLOR_YCbCrA, DXVAHDDDI_COLOR_YCbCrA structure [Display Devices], _DXVAHDDDI_COLOR_YCbCrA, d3dumddi/DXVAHDDDI_COLOR_YCbCrA, display.dxvahdddi_color_ycbcra
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: d3dumddi.h
req.include-header: D3dumddi.h
req.target-type: Windows
req.target-min-winverclnt: DXVAHDDDI_COLOR_YCbCrA is supported beginning with the Windows 7 operating system.
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
-	d3dumddi.h
api_name:
-	DXVAHDDDI_COLOR_YCbCrA
product:
- Windows
targetos: Windows
req.typenames: DXVAHDDDI_COLOR_YCbCrA
---

# _DXVAHDDDI_COLOR_YCbCrA structure


## -description


The DXVAHDDDI_COLOR_YCbCrA structure describes color in YCbCr terms.  


## -struct-fields




### -field Y

[in] A FLOAT value in the 0.0 to 1.0 range that is used to describe the luma component of the YCbCr color. 


### -field Cb

[in] A FLOAT value in the 0.0 to 1.0 range that is used to describe the blue chroma component of the YCbCr color. 


### -field Cr

[in] A FLOAT value in the 0.0 to 1.0 range that is used to describe the red chroma component of the YCbCr color. 


### -field A

[in] A FLOAT value in the 0.0 to 1.0 range that is used to describe the alpha component (that is, the transparency level) of the YCbCr color.


## -remarks



The setting of DXVAHDDDI_COLOR_YCbCrA for YCbCr black with opaque alpha is (0.0625, 0.5, 0.5, 1.0), which is (16, 128, 128, 255) when 8-bit presentation is used.

A DXVAHDDDI_COLOR_YCbCrA structure is specified in the <b>YCbCr</b> member of the <a href="https://msdn.microsoft.com/library/windows/hardware/ff563025">DXVAHDDDI_COLOR</a> union to specify the color in YCbCr terms.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff563025">DXVAHDDDI_COLOR</a>
 

 

