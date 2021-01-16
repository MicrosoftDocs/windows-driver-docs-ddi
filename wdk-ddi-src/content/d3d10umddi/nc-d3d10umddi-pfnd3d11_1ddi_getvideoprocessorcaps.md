---
UID: NC:d3d10umddi.PFND3D11_1DDI_GETVIDEOPROCESSORCAPS
title: PFND3D11_1DDI_GETVIDEOPROCESSORCAPS (d3d10umddi.h)
description: Queries the capabilities of a specified video processor.
old-location: display\getvideoprocessorcaps.htm
ms.date: 05/10/2018
keywords: ["PFND3D11_1DDI_GETVIDEOPROCESSORCAPS callback function"]
ms.keywords: PFND3D11_1DDI_GETVIDEOPROCESSORCAPS, PFND3D11_1DDI_GETVIDEOPROCESSORCAPS callback, d3d10umddi/pfnGetVideoProcessorCaps, display.getvideoprocessorcaps, pfnGetVideoProcessorCaps, pfnGetVideoProcessorCaps callback function [Display Devices]
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
 - PFND3D11_1DDI_GETVIDEOPROCESSORCAPS
 - d3d10umddi/PFND3D11_1DDI_GETVIDEOPROCESSORCAPS
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - D3d10umddi.h
api_name:
 - PFND3D11_1DDI_GETVIDEOPROCESSORCAPS
product:
 - Windows
---

# PFND3D11_1DDI_GETVIDEOPROCESSORCAPS callback function


## -description

Queries the capabilities of a specified video processor.

## -parameters

### -param Arg1

*hDevice* [in]

A handle to the display device (graphics context).

### -param Arg2

*hProcessorEnum* [in]

A handle to a video processor enumeration object that was created through a call to the <a href="/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d11_1ddi_createvideoprocessorenum">CreateVideoProcessorEnum</a> function.

### -param Arg3

*pCaps* [in, out]

A pointer to a <a href="/windows-hardware/drivers/ddi/d3d10umddi/ns-d3d10umddi-d3d11_1ddi_video_processor_caps">D3D11_1DDI_VIDEO_PROCESSOR_CAPS</a> structure that specifies the capabilities of the video processor that is specified by the <i>hProcessorEnum</i> parameter.

## -see-also

<a href="/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d11_1ddi_createvideoprocessorenum">CreateVideoProcessorEnum</a>



<a href="/windows-hardware/drivers/ddi/d3d10umddi/ns-d3d10umddi-d3d11_1ddi_video_processor_caps">D3D11_1DDI_VIDEO_PROCESSOR_CAPS</a>

