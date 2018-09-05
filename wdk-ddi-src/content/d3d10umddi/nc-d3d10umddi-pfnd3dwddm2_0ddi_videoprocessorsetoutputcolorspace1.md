---
UID: NC:d3d10umddi.PFND3DWDDM2_0DDI_VIDEOPROCESSORSETOUTPUTCOLORSPACE1
title: PFND3DWDDM2_0DDI_VIDEOPROCESSORSETOUTPUTCOLORSPACE1
author: windows-driver-content
description: Sets the color space information for the video processor output surface. This function must be implemented by Windows Display Driver Model (WDDM) 2.0, or later, drivers.
old-location: display\videoprocessorsetoutputcolorspace1.htm
ms.assetid: 03C45E7A-245C-4A04-9284-6D803CF0CC8F
ms.author: windowsdriverdev
ms.date: 5/10/2018
ms.keywords: PFND3DWDDM2_0DDI_VIDEOPROCESSORSETOUTPUTCOLORSPACE1, PFND3DWDDM2_0DDI_VIDEOPROCESSORSETOUTPUTCOLORSPACE1 callback, d3d10umddi/pfnVideoProcessorSetOutputColorSpace1, display.videoprocessorsetoutputcolorspace1, pfnVideoProcessorSetOutputColorSpace1, pfnVideoProcessorSetOutputColorSpace1 callback function [Display Devices]
ms.prod: windows-hardware
ms.technology: windows-devices
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
-	pfnVideoProcessorSetOutputColorSpace1
product:
- Windows
targetos: Windows
tech.root: display
req.typenames: 
---

# PFND3DWDDM2_0DDI_VIDEOPROCESSORSETOUTPUTCOLORSPACE1 callback function


## -description


Sets the color space information for the video processor output surface. This function must be implemented by Windows Display Driver Model (WDDM) 2.0, or later, drivers.


## -parameters




### -param hDevice [in]

 A handle to the display device (graphics context). The Direct3D runtime passed the user-mode driver this handle as the <b>hDevice</b> member of the <a href="https://msdn.microsoft.com/library/windows/hardware/ff542931">D3DDDIARG_CREATEDEVICE</a> structure at device creation.


### -param hVideoProcessor [in]

A handle to the video processor object. 


### -param ColorSpace [in]

Contains a <a href="https://msdn.microsoft.com/library/windows/hardware/dn906320">D3DDDI_COLOR_SPACE_TYPE</a> enumeration identifying the color space.


## -returns



This callback function does not return a value.




## -remarks



The legacy <a href="https://msdn.microsoft.com/library/windows/hardware/hh439782">VideoProcessorSetOutputColorSpace</a>device driver interface (DDI) will not be called for WDDM 2.0 drivers.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff542931">D3DDDIARG_CREATEDEVICE</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/dn906320">D3DDDI_COLOR_SPACE_TYPE</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh439782">VideoProcessorSetOutputColorSpace</a>
 

 

