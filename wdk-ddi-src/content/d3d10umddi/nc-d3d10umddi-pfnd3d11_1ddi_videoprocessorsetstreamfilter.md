---
UID: NC:d3d10umddi.PFND3D11_1DDI_VIDEOPROCESSORSETSTREAMFILTER
title: PFND3D11_1DDI_VIDEOPROCESSORSETSTREAMFILTER (d3d10umddi.h)
description: Enables or disables an image filter for an input stream on the video processor.
old-location: display\videoprocessorsetstreamfilter.htm
ms.date: 05/10/2018
keywords: ["PFND3D11_1DDI_VIDEOPROCESSORSETSTREAMFILTER callback function"]
ms.keywords: PFND3D11_1DDI_VIDEOPROCESSORSETSTREAMFILTER, PFND3D11_1DDI_VIDEOPROCESSORSETSTREAMFILTER callback, d3d10umddi/pfnVideoProcessorSetStreamFilter, display.videoprocessorsetstreamfilter, pfnVideoProcessorSetStreamFilter, pfnVideoProcessorSetStreamFilter callback function [Display Devices]
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
 - PFND3D11_1DDI_VIDEOPROCESSORSETSTREAMFILTER
 - d3d10umddi/PFND3D11_1DDI_VIDEOPROCESSORSETSTREAMFILTER
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - D3d10umddi.h
api_name:
 - PFND3D11_1DDI_VIDEOPROCESSORSETSTREAMFILTER
---

# PFND3D11_1DDI_VIDEOPROCESSORSETSTREAMFILTER callback function


## -description

Enables or disables an image filter for an input stream on the video processor.

## -parameters

### -param unnamedParam1

*hDevice* [in]

A handle to the display device (graphics context).

### -param unnamedParam2

*hVideoProcessor* [in]

A handle to the video processor object that was created through a call to the <a href="/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d11_1ddi_createvideoprocessor">CreateVideoProcessor</a> function.

### -param unnamedParam3

*StreamIndex* [in]

The zero-based index of the input stream.

### -param unnamedParam4

*Filter* [in]

The filter, specified as a <a href="/windows-hardware/drivers/ddi/d3d10umddi/ne-d3d10umddi-d3d11_1ddi_video_processor_filter">D3D11_1DDI_VIDEO_PROCESSOR_FILTER</a> value.

### -param unnamedParam5

*Enable* [in]

If <b>TRUE</b>, the filter is enabled on the video processor.

### -param unnamedParam6

*Level* [in]

The filter level. The meaning of this value is defined by the independent hardware vendor (IHV).

<div class="alert"><b>Note</b>  If the <i>Enable</i> parameter is FALSE, this parameter is ignored.

</div>
<div> </div>

## -see-also

<a href="/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d11_1ddi_createvideoprocessor">CreateVideoProcessor</a>



<a href="/windows-hardware/drivers/ddi/d3d10umddi/ne-d3d10umddi-d3d11_1ddi_video_processor_filter">D3D11_1DDI_VIDEO_PROCESSOR_FILTER</a>

