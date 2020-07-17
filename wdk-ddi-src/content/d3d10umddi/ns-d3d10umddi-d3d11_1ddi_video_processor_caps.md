---
UID: NS:d3d10umddi.D3D11_1DDI_VIDEO_PROCESSOR_CAPS
title: D3D11_1DDI_VIDEO_PROCESSOR_CAPS (d3d10umddi.h)
description: Describes the capabilities of a Microsoft Direct3D 11 video processor.
old-location: display\d3d11_1ddi_video_processor_caps.htm
ms.assetid: d825a0d1-fa58-4525-bf90-eb7eaee0cfba
ms.date: 05/10/2018
keywords: ["D3D11_1DDI_VIDEO_PROCESSOR_CAPS structure"]
ms.keywords: D3D11_1DDI_VIDEO_PROCESSOR_CAPS, D3D11_1DDI_VIDEO_PROCESSOR_CAPS structure [Display Devices], d3d10umddi/D3D11_1DDI_VIDEO_PROCESSOR_CAPS, display.d3d11_1ddi_video_processor_caps
f1_keywords:
 - "d3d10umddi/D3D11_1DDI_VIDEO_PROCESSOR_CAPS"
 - "D3D11_1DDI_VIDEO_PROCESSOR_CAPS"
req.header: d3d10umddi.h
req.include-header: D3d10umddi.h
req.target-type: Windows
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
topic_type:
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- D3d10umddi.h
api_name:
- D3D11_1DDI_VIDEO_PROCESSOR_CAPS
product:
- Windows
targetos: Windows
tech.root: display
req.typenames: D3D11_1DDI_VIDEO_PROCESSOR_CAPS
---

# D3D11_1DDI_VIDEO_PROCESSOR_CAPS structure


## -description


Describes the capabilities of a Microsoft Direct3D 11 video processor.


## -struct-fields




### -field DeviceCaps

A bitwise <b>OR</b> of zero or more flags from the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/ne-d3d10umddi-d3d11_1ddi_video_processor_device_caps">D3D11_1DDI_VIDEO_PROCESSOR_DEVICE_CAPS</a> enumeration.


### -field FeatureCaps

A bitwise <b>OR</b> of zero or more flags from the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/ne-d3d10umddi-d3d11_1ddi_video_processor_feature_caps">D3D11_1DDI_VIDEO_PROCESSOR_FEATURE_CAPS</a> enumeration.


### -field FilterCaps

A bitwise <b>OR</b> of zero or more flags from the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/ne-d3d10umddi-d3d11_1ddi_video_processor_filter_caps">D3D11_1DDI_VIDEO_PROCESSOR_FILTER_CAPS</a> enumeration.


### -field InputFormatCaps

A bitwise <b>OR</b> of zero or more flags from the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/ne-d3d10umddi-d3d11_1ddi_video_processor_format_caps">D3D11_1DDI_VIDEO_PROCESSOR_FORMAT_CAPS</a> enumeration.


### -field AutoStreamCaps

A bitwise <b>OR</b> of zero or more flags from the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/ne-d3d10umddi-d3d11_1ddi_video_processor_auto_stream_caps">D3D11_1DDI_VIDEO_PROCESSOR_AUTO_STREAM_CAPS</a> enumeration.


### -field StereoCaps

A bitwise <b>OR</b> of zero or more flags from the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/ne-d3d10umddi-d3d11_1ddi_video_processor_stereo_caps">D3D11_1DDI_VIDEO_PROCESSOR_STEREO_CAPS</a> enumeration.


### -field RateConversionCapsCount

The number of frame-rate conversion capabilities. To enumerate the frame-rate conversion capabilities, call the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d11_1ddi_getvideoprocessorrateconversioncaps">GetVideoProcessorRateConversionCaps</a> function.


### -field MaxInputStreams

The maximum number of input streams that can be enabled at the same time.


### -field MaxStreamStates

The maximum number of input streams for which the device can store state data.


## -remarks



The video processor stores state information for each input stream. These states persist between blits. With each blit, the application selects which streams to enable or disable. Disabling a stream does not affect the state information for that stream.

The <b>MaxStreamStates</b> member gives the maximum number of stream states that can be saved. The <b>MaxInputStreams</b> member gives the maximum number of streams that can be enabled during a blit. These two values can differ.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/ne-d3d10umddi-d3d11_1ddi_video_processor_auto_stream_caps">D3D11_1DDI_VIDEO_PROCESSOR_AUTO_STREAM_CAPS</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/ne-d3d10umddi-d3d11_1ddi_video_processor_device_caps">D3D11_1DDI_VIDEO_PROCESSOR_DEVICE_CAPS</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/ne-d3d10umddi-d3d11_1ddi_video_processor_feature_caps">D3D11_1DDI_VIDEO_PROCESSOR_FEATURE_CAPS</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/ne-d3d10umddi-d3d11_1ddi_video_processor_filter_caps">D3D11_1DDI_VIDEO_PROCESSOR_FILTER_CAPS</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/ne-d3d10umddi-d3d11_1ddi_video_processor_format_caps">D3D11_1DDI_VIDEO_PROCESSOR_FORMAT_CAPS</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/ne-d3d10umddi-d3d11_1ddi_video_processor_stereo_caps">D3D11_1DDI_VIDEO_PROCESSOR_STEREO_CAPS</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d11_1ddi_getvideoprocessorrateconversioncaps">GetVideoProcessorRateConversionCaps</a>
 

 

