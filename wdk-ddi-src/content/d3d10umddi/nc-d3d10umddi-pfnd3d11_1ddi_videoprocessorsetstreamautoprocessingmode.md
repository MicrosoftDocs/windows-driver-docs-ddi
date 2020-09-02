---
UID: NC:d3d10umddi.PFND3D11_1DDI_VIDEOPROCESSORSETSTREAMAUTOPROCESSINGMODE
title: PFND3D11_1DDI_VIDEOPROCESSORSETSTREAMAUTOPROCESSINGMODE (d3d10umddi.h)
description: Enables or disables automatic processing features for an input stream on the video processor.
old-location: display\videoprocessorsetstreamautoprocessingmode.htm
ms.assetid: 85c504e3-46b4-434a-8ab9-5c866eafe05a
ms.date: 05/10/2018
keywords: ["PFND3D11_1DDI_VIDEOPROCESSORSETSTREAMAUTOPROCESSINGMODE callback function"]
ms.keywords: PFND3D11_1DDI_VIDEOPROCESSORSETSTREAMAUTOPROCESSINGMODE, PFND3D11_1DDI_VIDEOPROCESSORSETSTREAMAUTOPROCESSINGMODE callback, d3d10umddi/pfnVideoProcessorSetStreamAutoProcessingMode, display.videoprocessorsetstreamautoprocessingmode, pfnVideoProcessorSetStreamAutoProcessingMode, pfnVideoProcessorSetStreamAutoProcessingMode callback function [Display Devices]
req.header: d3d10umddi.h
req.include-header: D3d10umddi.h
req.target-type: Desktop
req.target-min-winverclnt: Windows 8
req.target-min-winversvr: Windows Server 2012
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
 - PFND3D11_1DDI_VIDEOPROCESSORSETSTREAMAUTOPROCESSINGMODE
 - d3d10umddi/PFND3D11_1DDI_VIDEOPROCESSORSETSTREAMAUTOPROCESSINGMODE
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - D3d10umddi.h
api_name:
 - pfnVideoProcessorSetStreamAutoProcessingMode
---

# PFND3D11_1DDI_VIDEOPROCESSORSETSTREAMAUTOPROCESSINGMODE callback function


## -description

Enables or disables automatic processing features for an input stream on the video processor.

## -parameters

### -param Arg1

*hDevice* [in]

A handle to the display device (graphics context).

### -param Arg2

*hVideoProcessor* [in]

A handle to the video processor object that was created through a call to the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d11_1ddi_createvideoprocessor">CreateVideoProcessor</a> function.

### -param Arg3

*StreamIndex* [in]

The zero-based index of the input stream.

### -param Arg4

*Enable* [in]

If <b>TRUE</b>, automatic processing features are enabled. If <b>FALSE</b>, the driver disables any additional video processing that it might be performing.

## -remarks

By default, the driver might perform certain processing tasks automatically during the video processor bit-block transfer (bitblt). The <b>VideoProcessorSetStreamAutoProcessingMode</b> function enables the application to disable these additional video processing features that the driver may expose. 

For example, if the independent software vendor (ISV) provides its own pixel shader for the video processor, it might want to disable the driver's automatic processing.

## -see-also

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d11_1ddi_createvideoprocessor">CreateVideoProcessor</a>

