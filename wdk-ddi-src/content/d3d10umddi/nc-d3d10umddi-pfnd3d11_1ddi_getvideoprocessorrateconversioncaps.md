---
UID: NC:d3d10umddi.PFND3D11_1DDI_GETVIDEOPROCESSORRATECONVERSIONCAPS
title: PFND3D11_1DDI_GETVIDEOPROCESSORRATECONVERSIONCAPS (d3d10umddi.h)
description: Queries a specified group of video processing capabilities that are associated with frame-rate conversion, including deinterlacing and inverse telecine.
old-location: display\getvideoprocessorrateconversioncaps.htm
ms.date: 05/10/2018
keywords: ["PFND3D11_1DDI_GETVIDEOPROCESSORRATECONVERSIONCAPS callback function"]
ms.keywords: PFND3D11_1DDI_GETVIDEOPROCESSORRATECONVERSIONCAPS, PFND3D11_1DDI_GETVIDEOPROCESSORRATECONVERSIONCAPS callback, d3d10umddi/pfnGetVideoProcessorRateConversionCaps, display.getvideoprocessorrateconversioncaps, pfnGetVideoProcessorRateConversionCaps, pfnGetVideoProcessorRateConversionCaps callback function [Display Devices]
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
 - PFND3D11_1DDI_GETVIDEOPROCESSORRATECONVERSIONCAPS
 - d3d10umddi/PFND3D11_1DDI_GETVIDEOPROCESSORRATECONVERSIONCAPS
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - D3d10umddi.h
api_name:
 - PFND3D11_1DDI_GETVIDEOPROCESSORRATECONVERSIONCAPS
---

# PFND3D11_1DDI_GETVIDEOPROCESSORRATECONVERSIONCAPS callback function


## -description

Queries a specified group of video processing capabilities that are associated with frame-rate conversion, including deinterlacing and inverse telecine.

## -parameters

### -param unnamedParam1

*hDevice* [in]

A handle to the display device (graphics context).

### -param unnamedParam2

*hProcessorEnum* [in]

A handle to a video processor enumeration object that was created through a call to the <a href="/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d11_1ddi_createvideoprocessorenum">CreateVideoProcessorEnum</a> function.

### -param unnamedParam3

*RateConversionIndex* [in]

The zero-based index of the frame-rate conversion capability group. For more information, see the Remarks section.

### -param unnamedParam4

*pCaps* [out]

A pointer to a <a href="/windows-hardware/drivers/ddi/d3d10umddi/ns-d3d10umddi-d3d11_1ddi_video_processor_rate_conversion_caps">D3D11_1DDI_VIDEO_PROCESSOR_RATE_CONVERSION_CAPS</a> structure that contains the attributes of  the specified rate conversion capability group.

## -remarks

The display miniport driver returns the maximum number of frame-rate conversion capabilities that it supports through the <b>RateConversionCapsCount</b> member of the <a href="/windows-hardware/drivers/ddi/d3d10umddi/ns-d3d10umddi-d3d11_1ddi_video_processor_caps">D3D11_1DDI_VIDEO_PROCESSOR_CAPS</a> structure. The driver returns a pointer to this structure through its <a href="/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d11_1ddi_getvideoprocessorcaps">GetVideoProcessorCaps</a> function.

## -see-also

<a href="/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d11_1ddi_createvideoprocessorenum">CreateVideoProcessorEnum</a>



<a href="/windows-hardware/drivers/ddi/d3d10umddi/ns-d3d10umddi-d3d11_1ddi_video_processor_caps">D3D11_1DDI_VIDEO_PROCESSOR_CAPS</a>



<a href="/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d11_1ddi_getvideoprocessorcaps">GetVideoProcessorCaps</a>

