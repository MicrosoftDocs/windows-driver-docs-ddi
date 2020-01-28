---
UID: NC:d3d10umddi.PFND3D11_1DDI_GETVIDEOPROCESSORFILTERRANGE
title: PFND3D11_1DDI_GETVIDEOPROCESSORFILTERRANGE (d3d10umddi.h)
description: Queries the range of values that the display miniport driver supports for a specified video processor filter.
old-location: display\getvideoprocessorfilterrange.htm
ms.assetid: ab3f8abb-4735-42c1-9664-8f2f5f7d5da7
ms.date: 05/10/2018
ms.keywords: PFND3D11_1DDI_GETVIDEOPROCESSORFILTERRANGE, PFND3D11_1DDI_GETVIDEOPROCESSORFILTERRANGE callback, d3d10umddi/pfnGetVideoProcessorFilterRange, display.getvideoprocessorfilterrange, pfnGetVideoProcessorFilterRange, pfnGetVideoProcessorFilterRange callback function [Display Devices]
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
 - "d3d10umddi/pfnGetVideoProcessorFilterRange"
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - D3d10umddi.h
api_name:
 - pfnGetVideoProcessorFilterRange
product:
 - Windows
---

# PFND3D11_1DDI_GETVIDEOPROCESSORFILTERRANGE callback function

## -description

Queries the range of values that the display miniport driver supports for a specified video processor filter.

## -parameters

### -param Arg1

*hDevice* [in]

A handle to the display device (graphics context).

### -param Arg2

*hProcessorEnum* [in]

A handle to a video processor enumeration object that was created through a call to the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d11_1ddi_createvideoprocessorenum">CreateVideoProcessorEnum</a> function.

### -param Arg3

*Filter* [in]

The type of the video processor filter, specified as a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/ne-d3d10umddi-d3d11_1ddi_video_processor_filter">D3D11_1DDI_VIDEO_PROCESSOR_FILTER</a> value.

### -param Arg4

*pFilterRange* [out]

A pointer to a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/ns-d3d10umddi-d3d11_1ddi_video_processor_filter_range">D3D11_1DDI_VIDEO_PROCESSOR_FILTER_RANGE</a> structure that specifies the range of values for the specified filter.

## -see-also

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d11_1ddi_createvideoprocessorenum">CreateVideoProcessorEnum</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/ne-d3d10umddi-d3d11_1ddi_video_processor_filter">D3D11_1DDI_VIDEO_PROCESSOR_FILTER</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/ns-d3d10umddi-d3d11_1ddi_video_processor_filter_range">D3D11_1DDI_VIDEO_PROCESSOR_FILTER_RANGE</a>

