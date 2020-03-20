---
UID: NC:d3d10umddi.PFND3DWDDM2_0DDI_VIDEOPROCESSORSETSTREAMCOLORSPACE1
title: PFND3DWDDM2_0DDI_VIDEOPROCESSORSETSTREAMCOLORSPACE1 (d3d10umddi.h)
description: Sets the color space information for the video processor input stream. This function must be implemented by Windows Display Driver Model (WDDM) 2.0, or later, drivers.
old-location: display\videoprocessorsetstreamcolorspace1.htm
ms.assetid: BFE62398-DDAE-4DC1-9DB3-6B71BBDD506D
ms.date: 05/10/2018
keywords: ["PFND3DWDDM2_0DDI_VIDEOPROCESSORSETSTREAMCOLORSPACE1 callback function"]
ms.keywords: PFND3DWDDM2_0DDI_VIDEOPROCESSORSETSTREAMCOLORSPACE1, PFND3DWDDM2_0DDI_VIDEOPROCESSORSETSTREAMCOLORSPACE1 callback, d3d10umddi/pfnVideoProcessorSetStreamColorSpace1, display.videoprocessorsetstreamcolorspace1, pfnVideoProcessorSetStreamColorSpace1, pfnVideoProcessorSetStreamColorSpace1 callback function [Display Devices]
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
targetos: Windows
tech.root: display
req.typenames: 
f1_keywords:
 - "d3d10umddi/pfnVideoProcessorSetStreamColorSpace1"
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - D3d10umddi.h
api_name:
 - pfnVideoProcessorSetStreamColorSpace1
product:
 - Windows
---

# PFND3DWDDM2_0DDI_VIDEOPROCESSORSETSTREAMCOLORSPACE1 callback function

## -description

Sets the color space information for the video processor input stream. This function must be implemented by Windows Display Driver Model (WDDM) 2.0, or later, drivers.

## -parameters

### -param hDevice

A handle to the display device (graphics context). The Direct3D runtime passed the user-mode driver this handle as the <b>hDevice</b> member of the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dumddi/ns-d3dumddi-_d3dddiarg_createdevice">D3DDDIARG_CREATEDEVICE</a> structure at device creation.

### -param hVideoProcessor

A handle to the video processor object.

### -param StreamIndex

Indicates the input stream.

### -param ColorSpace

Contains a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dukmdt/ne-d3dukmdt-d3dddi_color_space_type">D3DDDI_COLOR_SPACE_TYPE</a> enumeration value identifying the color space.

## -remarks

The legacy <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d11_1ddi_videoprocessorsetstreamcolorspace">VideoProcessorSetStreamColorSpace</a>device driver interface (DDI) will not be called for WDDM 2.0 drivers.

## -see-also

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dumddi/ns-d3dumddi-_d3dddiarg_createdevice">D3DDDIARG_CREATEDEVICE</a>

