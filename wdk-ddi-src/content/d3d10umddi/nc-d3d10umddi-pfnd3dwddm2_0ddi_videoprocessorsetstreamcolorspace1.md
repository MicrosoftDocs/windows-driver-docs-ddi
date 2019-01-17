---
UID: NC:d3d10umddi.PFND3DWDDM2_0DDI_VIDEOPROCESSORSETSTREAMCOLORSPACE1
title: PFND3DWDDM2_0DDI_VIDEOPROCESSORSETSTREAMCOLORSPACE1
description: Sets the color space information for the video processor input stream. This function must be implemented by Windows Display Driver Model (WDDM) 2.0, or later, drivers.
old-location: display\videoprocessorsetstreamcolorspace1.htm
ms.assetid: BFE62398-DDAE-4DC1-9DB3-6B71BBDD506D
ms.date: 05/10/2018
ms.keywords: PFND3DWDDM2_0DDI_VIDEOPROCESSORSETSTREAMCOLORSPACE1, PFND3DWDDM2_0DDI_VIDEOPROCESSORSETSTREAMCOLORSPACE1 callback, d3d10umddi/pfnVideoProcessorSetStreamColorSpace1, display.videoprocessorsetstreamcolorspace1, pfnVideoProcessorSetStreamColorSpace1, pfnVideoProcessorSetStreamColorSpace1 callback function [Display Devices]
ms.topic: callback
req.header: d3d10umddi.h
req.include-header: D3d10umddi.h
req.target-type: Desktop
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
-	APIRef
-	kbSyntax
api_type:
-	UserDefined
api_location:
-	D3d10umddi.h
api_name:
-	pfnVideoProcessorSetStreamColorSpace1
product:
- Windows
targetos: Windows
tech.root: display
req.typenames: 
---

# PFND3DWDDM2_0DDI_VIDEOPROCESSORSETSTREAMCOLORSPACE1 callback function


## -description


Sets the color space information for the video processor input stream. This function must be implemented by Windows Display Driver Model (WDDM) 2.0, or later, drivers.


## -parameters




### -param hDevice [in]

A handle to the display device (graphics context). The Direct3D runtime passed the user-mode driver this handle as the <b>hDevice</b> member of the <a href="https://msdn.microsoft.com/library/windows/hardware/ff542931">D3DDDIARG_CREATEDEVICE</a> structure at device creation.


### -param hVideoProcessor [in]

A handle to the video processor object. 


### -param StreamIndex [in]

Indicates the input stream.


### -param ColorSpace [in]

Contains a <a href="https://msdn.microsoft.com/library/windows/hardware/dn906320">D3DDDI_COLOR_SPACE_TYPE</a> enumeration value identifying the color space.


## -returns



This callback function does not return a value.




## -remarks



The legacy <a href="https://msdn.microsoft.com/library/windows/hardware/hh439796">VideoProcessorSetStreamColorSpace</a>device driver interface (DDI) will not be called for WDDM 2.0 drivers.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff542931">D3DDDIARG_CREATEDEVICE</a>
 

 

