---
UID: NC:d3d10umddi.PFND3D11_1DDI_GETVIDEOPROCESSORCUSTOMRATE
title: PFND3D11_1DDI_GETVIDEOPROCESSORCUSTOMRATE (d3d10umddi.h)
description: Queries a custom frame rate that is associated with a rate conversion capability group.
old-location: display\getvideoprocessorcustomrate.htm
ms.date: 05/10/2018
keywords: ["PFND3D11_1DDI_GETVIDEOPROCESSORCUSTOMRATE callback function"]
ms.keywords: PFND3D11_1DDI_GETVIDEOPROCESSORCUSTOMRATE, PFND3D11_1DDI_GETVIDEOPROCESSORCUSTOMRATE callback, d3d10umddi/pfnGetVideoProcessorCustomRate, display.getvideoprocessorcustomrate, pfnGetVideoProcessorCustomRate, pfnGetVideoProcessorCustomRate callback function [Display Devices]
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
 - PFND3D11_1DDI_GETVIDEOPROCESSORCUSTOMRATE
 - d3d10umddi/PFND3D11_1DDI_GETVIDEOPROCESSORCUSTOMRATE
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - D3d10umddi.h
api_name:
 - PFND3D11_1DDI_GETVIDEOPROCESSORCUSTOMRATE
---

# PFND3D11_1DDI_GETVIDEOPROCESSORCUSTOMRATE callback function


## -description

Queries a custom frame rate that is associated with a rate conversion capability group.

## -parameters

### -param unnamedParam1

*hDevice* [in]

A handle to the display device (graphics context).

### -param unnamedParam2

*hProcessorEnum* [in]

A handle to a video processor enumeration object that was created through a call to the <a href="/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d11_1ddi_createvideoprocessorenum">CreateVideoProcessorEnum</a> function.

### -param unnamedParam3

*CustomRateIndex* [in]

The zero-based index of the custom rate to query. For more information, see the Remarks section.

### -param unnamedParam4

*RateConversionIndex* [in]

The zero-based index of the frame-rate conversion capability group. For more information, see the Remarks section.

### -param unnamedParam5

*pRate* [out]

A pointer to a <a href="/windows-hardware/drivers/ddi/d3d10umddi/ns-d3d10umddi-d3d11_1ddi_video_processor_custom_rate">D3D11_1DDI_VIDEO_PROCESSOR_CUSTOM_RATE</a> structure that contains the attributes of the specified custom rate.

## -remarks

The display miniport driver returns the maximum number of frame-rate conversion capabilities that it supports through the <b>RateConversionCapsCount</b> member of the <a href="/windows-hardware/drivers/ddi/d3d10umddi/ns-d3d10umddi-d3d11_1ddi_video_processor_caps">D3D11_1DDI_VIDEO_PROCESSOR_CAPS</a> structure. The driver returns a pointer to this structure through its <a href="/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d11_1ddi_getvideoprocessorcaps">GetVideoProcessorCaps</a> function. In addition, the attributes of a frame-rate conversion capability group can be queried by calling the <b>GetVideoProcessorCaps</b> function.

The display miniport driver returns the maximum number of custom rates that it supports through the <b>CustomRateCount</b> member of the <a href="/windows-hardware/drivers/ddi/d3d10umddi/ns-d3d10umddi-d3d11_1ddi_video_processor_rate_conversion_caps">D3D11_1DDI_VIDEO_PROCESSOR_RATE_CONVERSION_CAPS</a> structure. The driver returns a pointer to this structure through its <a href="/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d11_1ddi_getvideoprocessorcaps">GetVideoProcessorCaps</a> function. In addition, the attributes of a frame-rate conversion capability group can be queried by calling the <a href="/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d11_1ddi_getvideoprocessorrateconversioncaps">GetVideoProcessorRateConversionCaps</a> function.

## -see-also

<a href="/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d11_1ddi_createvideoprocessorenum">CreateVideoProcessorEnum</a>



<a href="/windows-hardware/drivers/ddi/d3d10umddi/ns-d3d10umddi-d3d11_1ddi_video_processor_caps">D3D11_1DDI_VIDEO_PROCESSOR_CAPS</a>



<a href="/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d11_1ddi_getvideoprocessorcaps">GetVideoProcessorCaps</a>



<a href="/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d11_1ddi_getvideoprocessorrateconversioncaps">GetVideoProcessorRateConversionCaps</a>

