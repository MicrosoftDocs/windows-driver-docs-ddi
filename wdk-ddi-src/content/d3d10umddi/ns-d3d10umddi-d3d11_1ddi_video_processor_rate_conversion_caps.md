---
UID: NS:d3d10umddi.D3D11_1DDI_VIDEO_PROCESSOR_RATE_CONVERSION_CAPS
title: D3D11_1DDI_VIDEO_PROCESSOR_RATE_CONVERSION_CAPS (d3d10umddi.h)
description: Defines a group of video processor capabilities that are associated with frame-rate conversion, including deinterlacing and inverse telecine.
old-location: display\d3d11_1ddi_video_processor_rate_conversion_caps.htm
ms.assetid: 1b66f203-1c74-4b5e-82ae-7dfdc88da2b4
ms.date: 05/10/2018
keywords: ["D3D11_1DDI_VIDEO_PROCESSOR_RATE_CONVERSION_CAPS structure"]
ms.keywords: D3D11_1DDI_VIDEO_PROCESSOR_RATE_CONVERSION_CAPS, D3D11_1DDI_VIDEO_PROCESSOR_RATE_CONVERSION_CAPS structure [Display Devices], d3d10umddi/D3D11_1DDI_VIDEO_PROCESSOR_RATE_CONVERSION_CAPS, display.d3d11_1ddi_video_processor_rate_conversion_caps
f1_keywords:
 - "d3d10umddi/D3D11_1DDI_VIDEO_PROCESSOR_RATE_CONVERSION_CAPS"
 - "D3D11_1DDI_VIDEO_PROCESSOR_RATE_CONVERSION_CAPS"
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
- D3D11_1DDI_VIDEO_PROCESSOR_RATE_CONVERSION_CAPS
targetos: Windows
tech.root: display
req.typenames: D3D11_1DDI_VIDEO_PROCESSOR_RATE_CONVERSION_CAPS
---

# D3D11_1DDI_VIDEO_PROCESSOR_RATE_CONVERSION_CAPS structure


## -description


Defines a group of video processor capabilities that are associated with frame-rate conversion, including deinterlacing and inverse telecine.


## -struct-fields




### -field PastFrames

The number of past reference frames required to perform the optimal video processing.


### -field FutureFrames

The number of future reference frames required to perform the optimal video processing.


### -field ConversionCaps

A bitwise <b>OR</b> of zero or more member values from the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/ne-d3d10umddi-d3d11_1ddi_video_processor_conversion_caps">D3D11_1DDI_VIDEO_PROCESSOR_CONVERSION_CAPS</a> structure.


### -field ITelecineCaps

A bitwise <b>OR</b> of zero or more constant values from the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/ne-d3d10umddi-d3d11_1ddi_video_processor_itelecine_caps">D3D11_1DDI_VIDEO_PROCESSOR_ITELECINE_CAPS</a> enumeration.


### -field CustomRateCount

The number of custom frame rates that the driver supports. To get the list of custom frame rates, call the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d11_1ddi_getvideoprocessorcustomrate">GetVideoProcessorCustomRate</a> function.


## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/ne-d3d10umddi-d3d11_1ddi_video_processor_conversion_caps">D3D11_1DDI_VIDEO_PROCESSOR_CONVERSION_CAPS</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/ne-d3d10umddi-d3d11_1ddi_video_processor_itelecine_caps">D3D11_1DDI_VIDEO_PROCESSOR_ITELECINE_CAPS</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/ns-d3d10umddi-d3d11_1ddi_video_processor_rate_conversion_caps">D3D11_1DDI_VIDEO_PROCESSOR_RATE_CONVERSION_CAPS</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d11_1ddi_getvideoprocessorcustomrate">GetVideoProcessorCustomRate</a>
 

 

