---
UID: NC:d3d10umddi.PFND3D11_1DDI_VIDEOPROCESSORSETSTREAMOUTPUTRATE
title: PFND3D11_1DDI_VIDEOPROCESSORSETSTREAMOUTPUTRATE (d3d10umddi.h)
description: Sets the rate at which the video processor produces output frames for an input stream.
old-location: display\videoprocessorsetstreamoutputrate.htm
ms.date: 12/09/2021
keywords: ["PFND3D11_1DDI_VIDEOPROCESSORSETSTREAMOUTPUTRATE callback function"]
ms.keywords: PFND3D11_1DDI_VIDEOPROCESSORSETSTREAMOUTPUTRATE, PFND3D11_1DDI_VIDEOPROCESSORSETSTREAMOUTPUTRATE callback, d3d10umddi/pfnVideoProcessorSetStreamOutputRate, display.videoprocessorsetstreamoutputrate, pfnVideoProcessorSetStreamOutputRate, pfnVideoProcessorSetStreamOutputRate callback function [Display Devices]
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
 - PFND3D11_1DDI_VIDEOPROCESSORSETSTREAMOUTPUTRATE
 - d3d10umddi/PFND3D11_1DDI_VIDEOPROCESSORSETSTREAMOUTPUTRATE
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - D3d10umddi.h
api_name:
 - PFND3D11_1DDI_VIDEOPROCESSORSETSTREAMOUTPUTRATE
product:
 - Windows
---

# PFND3D11_1DDI_VIDEOPROCESSORSETSTREAMOUTPUTRATE callback function

## -description

Sets the rate at which the video processor produces output frames for an input stream.

## -parameters

### -param unnamedParam1

*hDevice* [in]

A handle to the display device (graphics context).

### -param unnamedParam2

*hVideoProcessor* [in]

A handle to the video processor object that was created through a call to the [**CreateVideoProcessor**](nc-d3d10umddi-pfnd3d11_1ddi_createvideoprocessor.md) function.

### -param unnamedParam3

*StreamIndex* [in]

The zero-based index of the input stream.

### -param unnamedParam4

*RepeatFrame* [in]

Specifies how the driver performs frame-rate conversion, if it is required.

If the **RepeatFrame** parameter is TRUE, the driver should repeat frames.

If the **RepeatFrame** parameter is FALSE,  the driver should interpolate frames.

> [!NOTE]
>
> If **VideoProcessorSetStreamOutputRate** is never called, the driver should interpolate frames by default.

### -param unnamedParam5

*OutputRate* [in]

The output rate, specified as a [**D3D11_1DDI_VIDEO_PROCESSOR_OUTPUT_RATE**](ne-d3d10umddi-d3d11_1ddi_video_processor_output_rate.md) value.

For more information, see the Remarks section.

### -param unnamedParam6

*pCustomRate* [in]

A pointer to a [**DXGI_RATIONAL**](/windows/win32/api/dxgicommon/ns-dxgicommon-dxgi_rational) structure. If the **OutputRate** parameter is set to **D3D11_VIDEO_PROCESSOR_OUTPUT_RATE_CUSTOM**, this parameter specifies the exact output rate. Otherwise, this parameter is ignored and can be set to NULL.

## -remarks

The standard output rates that are defined by [**D3D11_1DDI_VIDEO_PROCESSOR_OUTPUT_RATE**](ne-d3d10umddi-d3d11_1ddi_video_processor_output_rate.md) enumeration values are normal frame-rate (**D3D11_1DDI_VIDEO_PROCESSOR_OUTPUT_RATE_NORMAL**) and half frame-rate (**D3D11_1DDI_VIDEO_PROCESSOR_OUTPUT_RATE_HALF**).

If the driver supports custom rates for rate conversion or inverse telecine, it can use a custom rate if the **OutputRate** parameter is set to **D3D11_1DDI_VIDEO_PROCESSOR_OUTPUT_RATE_CUSTOM**. The custom rate is specified by the **pCustomRate** parameter.

> [!NOTE]
>
> The driver reports its custom rates  in the [**D3D11_1DDI_VIDEO_PROCESSOR_CAPS**](ns-d3d10umddi-d3d11_1ddi_video_processor_caps.md) structure that is returned through the [**GetVideoProcessorCustomRate**](nc-d3d10umddi-pfnd3d11_1ddi_getvideoprocessorcustomrate.md) function.

Depending on the output rate, the driver might have to convert the frame rate. If so, the value of the **RepeatFrame** parameter controls whether the driver creates interpolated frames or repeats input frames.

## -see-also

[**CreateVideoProcessor**](nc-d3d10umddi-pfnd3d11_1ddi_createvideoprocessor.md)

[**D3D11_1DDI_VIDEO_PROCESSOR_CAPS**](ns-d3d10umddi-d3d11_1ddi_video_processor_caps.md)

[**D3D11_1DDI_VIDEO_PROCESSOR_OUTPUT_RATE**](ne-d3d10umddi-d3d11_1ddi_video_processor_output_rate.md)

[**DXGI_RATIONAL**](/windows/win32/api/dxgicommon/ns-dxgicommon-dxgi_rational)

[**GetVideoProcessorCustomRate**](nc-d3d10umddi-pfnd3d11_1ddi_getvideoprocessorcustomrate.md)
