---
UID: NC:d3d10umddi.PFND3D11_1DDI_VIDEOPROCESSORSETSTREAMDESTRECT
title: PFND3D11_1DDI_VIDEOPROCESSORSETSTREAMDESTRECT (d3d10umddi.h)
description: Sets the destination rectangle for an input stream on the video processor.
old-location: display\videoprocessorsetstreamdestrect.htm
ms.assetid: 84AD6C4F-A674-4CCC-B2E9-378E3E55EEF3
ms.date: 05/10/2018
keywords: ["PFND3D11_1DDI_VIDEOPROCESSORSETSTREAMDESTRECT callback function"]
ms.keywords: PFND3D11_1DDI_VIDEOPROCESSORSETSTREAMDESTRECT, PFND3D11_1DDI_VIDEOPROCESSORSETSTREAMDESTRECT callback, d3d10umddi/pfnVideoProcessorSetStreamDestRect, display.videoprocessorsetstreamdestrect, pfnVideoProcessorSetStreamDestRect, pfnVideoProcessorSetStreamDestRect callback function [Display Devices]
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
 - "d3d10umddi/pfnVideoProcessorSetStreamDestRect"
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - D3d10umddi.h
api_name:
 - pfnVideoProcessorSetStreamDestRect
product:
 - Windows
---

# PFND3D11_1DDI_VIDEOPROCESSORSETSTREAMDESTRECT callback function

## -description

Sets the destination rectangle for an input stream on the video processor.

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

If <b>TRUE</b>, the destination rectangle specified by the <i>pDestRect</i> parameter should be used by the video processor.

### -param Arg5

*pDestRect* [in]

A pointer to a <a href="https://docs.microsoft.com/windows/desktop/api/windef/ns-windef-tagrect">RECT</a> structure that specifies the destination rectangle.

<div class="alert"><b>Note</b>  If the <i>Enable</i> parameter is <b>FALSE</b>, this parameter is ignored.</div>
<div> </div>

## -remarks

The destination rectangle is the portion of the output surface that receives the bit-block transfer (bitblt) for the specified input stream. The destination rectangle is given in pixel coordinates, relative to the output surface.

The default destination rectangle is an empty rectangle (0, 0, 0, 0). If the <i>VideoProcessorSetStreamDestRect</i> function is never called, or if the <i>Enable</i> parameter is <b>FALSE</b>, no data is written from the specified input stream.

## -see-also

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dumddi/nc-d3dumddi-pfnd3dddi_dxvahd_createvideoprocessor">CreateVideoProcessor</a>



<a href="https://docs.microsoft.com/windows/desktop/api/windef/ns-windef-tagrect">RECT</a>

