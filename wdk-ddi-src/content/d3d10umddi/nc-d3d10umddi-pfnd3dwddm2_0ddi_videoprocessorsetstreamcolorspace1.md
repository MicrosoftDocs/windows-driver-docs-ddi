---
UID: NC:d3d10umddi.PFND3DWDDM2_0DDI_VIDEOPROCESSORSETSTREAMCOLORSPACE1
title: PFND3DWDDM2_0DDI_VIDEOPROCESSORSETSTREAMCOLORSPACE1
author: windows-driver-content
description: Sets the colorspace information for the video processor input stream. This function must be implemented by Windows Display Driver Model (WDDM) 2.0, or later, drivers.
old-location: display\videoprocessorsetstreamcolorspace1.htm
old-project: display
ms.assetid: BFE62398-DDAE-4DC1-9DB3-6B71BBDD506D
ms.author: windowsdriverdev
ms.date: 2/20/2018
ms.keywords: display.videoprocessorsetstreamcolorspace1, pfnVideoProcessorSetStreamColorSpace1 callback function [Display Devices], pfnVideoProcessorSetStreamColorSpace1, PFND3DWDDM2_0DDI_VIDEOPROCESSORSETSTREAMCOLORSPACE1, PFND3DWDDM2_0DDI_VIDEOPROCESSORSETSTREAMCOLORSPACE1, d3d10umddi/pfnVideoProcessorSetStreamColorSpace1
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	UserDefined
apilocation:
-	D3d10umddi.h
apiname:
-	pfnVideoProcessorSetStreamColorSpace1
product: Windows
targetos: Windows
req.typenames: "*PSETRESULT_INFO, SETRESULT_INFO"
---

# PFND3DWDDM2_0DDI_VIDEOPROCESSORSETSTREAMCOLORSPACE1 callback


## -description


Sets the colorspace information for the video processor input stream. This function must be implemented by Windows Display Driver Model (WDDM) 2.0, or later, drivers.


## -prototype


````
PFND3DWDDM2_0DDI_VIDEOPROCESSORSETSTREAMCOLORSPACE1 pfnVideoProcessorSetStreamColorSpace1;

VOID APIENTRY* pfnVideoProcessorSetStreamColorSpace1(
  _In_ D3D10DDI_HDEVICE           hDevice,
  _In_ D3D11_1DDI_HVIDEOPROCESSOR hVideoProcessor,
  _In_ UINT                       StreamIndex,
  _In_ D3DDDI_COLOR_SPACE_TYPE    ColorSpace
)
{ ... }
````


## -parameters




### -param hDevice [in]

 A handle to the display device (graphics context). The Direct3D runtime passed the user-mode driver this handle as the <b>hDevice</b> member of the <a href="..\d3dumddi\ns-d3dumddi-_d3dddiarg_createdevice.md">D3DDDIARG_CREATEDEVICE</a> structure at device creation.


### -param hVideoProcessor [in]

A handle to the video processor object. 


### -param StreamIndex [in]

Indicates the input stream.


### -param ColorSpace [in]

Contains a <a href="..\d3dukmdt\ne-d3dukmdt-d3dddi_color_space_type.md">D3DDDI_COLOR_SPACE_TYPE</a> enumeration value identifying the color space.


## -returns



This callback function does not return a value.




## -remarks



The legacy <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d11_1ddi_videoprocessorsetstreamcolorspace.md">VideoProcessorSetStreamColorSpace</a>device driver interface (DDI) will not be called for WDDM 2.0 drivers.




## -see-also

<a href="..\d3dumddi\ns-d3dumddi-_d3dddiarg_createdevice.md">D3DDDIARG_CREATEDEVICE</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20PFND3DWDDM2_0DDI_VIDEOPROCESSORSETSTREAMCOLORSPACE1 callback function%20 RELEASE:%20(2/20/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

