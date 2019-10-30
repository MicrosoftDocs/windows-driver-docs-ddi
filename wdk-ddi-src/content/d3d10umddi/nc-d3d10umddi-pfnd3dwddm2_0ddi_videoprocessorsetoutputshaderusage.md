---
UID: NC:d3d10umddi.PFND3DWDDM2_0DDI_VIDEOPROCESSORSETOUTPUTSHADERUSAGE
title: PFND3DWDDM2_0DDI_VIDEOPROCESSORSETOUTPUTSHADERUSAGE (d3d10umddi.h)
description: Sets the color space information for the video processor output surface. Optional for Windows Display Driver Model (WDDM) 2.0, or later, drivers.
old-location: display\videoprocessorsetoutputshaderusage.htm
ms.assetid: 320618F6-DE98-45D0-8015-DE24689D24D2
ms.date: 05/10/2018
ms.keywords: PFND3DWDDM2_0DDI_VIDEOPROCESSORSETOUTPUTSHADERUSAGE, PFND3DWDDM2_0DDI_VIDEOPROCESSORSETOUTPUTSHADERUSAGE callback, d3d10umddi/pfnVideoProcessorSetOutputShaderUsage, display.videoprocessorsetoutputshaderusage, pfnVideoProcessorSetOutputShaderUsage, pfnVideoProcessorSetOutputShaderUsage callback function [Display Devices]
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
targetos: Windows
tech.root: display
req.typenames: 
f1_keywords:
 - "d3d10umddi/pfnVideoProcessorSetOutputShaderUsage"
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - D3d10umddi.h
api_name:
 - pfnVideoProcessorSetOutputShaderUsage
product:
 - Windows
---

# PFND3DWDDM2_0DDI_VIDEOPROCESSORSETOUTPUTSHADERUSAGE callback function

## -description

Sets the color space information for the video processor output surface. Optional for Windows Display Driver Model (WDDM) 2.0, or later, drivers.

## -parameters

### -param hDevice

A handle to the display device (graphics context). The Direct3D runtime passed the user-mode driver this handle as the <b>hDevice</b> member of the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dumddi/ns-d3dumddi-_d3dddiarg_createdevice">D3DDDIARG_CREATEDEVICE</a> structure at device creation.

### -param hVideoProcessor

A handle to the video processor object.

### -param ShaderUsage

Indicates whether the output of <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d11_1ddi_videoprocessorblt">VideoProcessorBlt</a> may be read by Direct3D shaders.

<div class="alert"><b>Note</b>  This will always be <b>TRUE</b> unless multi-plane overlay hardware exists.</div>
<div> </div>

## -returns

This callback function does not return a value.

## -see-also

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dumddi/ns-d3dumddi-_d3dddiarg_createdevice">D3DDDIARG_CREATEDEVICE</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d11_1ddi_videoprocessorblt">VideoProcessorBlt</a>

