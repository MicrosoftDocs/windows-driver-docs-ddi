---
UID: NC:d3d10umddi.PFND3D11_1DDI_VIDEOPROCESSORSETOUTPUTTARGETRECT
title: PFND3D11_1DDI_VIDEOPROCESSORSETOUTPUTTARGETRECT (d3d10umddi.h)
description: Sets the target rectangle for the video processor.
old-location: display\videoprocessorsetoutputtargetrect.htm
ms.date: 05/10/2018
keywords: ["PFND3D11_1DDI_VIDEOPROCESSORSETOUTPUTTARGETRECT callback function"]
ms.keywords: PFND3D11_1DDI_VIDEOPROCESSORSETOUTPUTTARGETRECT, PFND3D11_1DDI_VIDEOPROCESSORSETOUTPUTTARGETRECT callback, d3d10umddi/pfnVideoProcessorSetOutputTargetRect, display.videoprocessorsetoutputtargetrect, pfnVideoProcessorSetOutputTargetRect, pfnVideoProcessorSetOutputTargetRect callback function [Display Devices]
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
 - PFND3D11_1DDI_VIDEOPROCESSORSETOUTPUTTARGETRECT
 - d3d10umddi/PFND3D11_1DDI_VIDEOPROCESSORSETOUTPUTTARGETRECT
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - D3d10umddi.h
api_name:
 - PFND3D11_1DDI_VIDEOPROCESSORSETOUTPUTTARGETRECT
---

# PFND3D11_1DDI_VIDEOPROCESSORSETOUTPUTTARGETRECT callback function


## -description

Sets the target rectangle for the video processor.

## -parameters

### -param unnamedParam1

*hDevice* [in]

A handle to the display device (graphics context).

### -param unnamedParam2

*hVideoProcessor* [in]

A handle to the video processor object that was created through a call to the <a href="/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d11_1ddi_createvideoprocessor">CreateVideoProcessor</a> function.

### -param unnamedParam3

*Enable* [in]

If <b>TRUE</b>, the target rectangle specified by the <i>pOutputRect</i> parameter should be used by the video processor.

### -param unnamedParam4

*pOutputRect* [in]

A  pointer to a <a href="/windows/win32/api/windef/ns-windef-rect">RECT</a> structure that specifies the target rectangle. 

<div class="alert"><b>Note</b>  If the <i>Enable</i> parameter is FALSE, this parameter is ignored.

</div>
<div> </div>

## -remarks

The target rectangle is the area within the destination surface where the output will be drawn. The target rectangle is given in pixel coordinates, relative to the destination surface.



If this function is never called, or if the <i>Enable</i> parameter is FALSE, the video processor writes to the entire destination surface.

## -see-also

<a href="/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d11_1ddi_createvideoprocessor">CreateVideoProcessor</a>



<a href="/windows/win32/api/windef/ns-windef-rect">RECT</a>

