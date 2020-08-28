---
UID: NS:d3d10umddi.D3DWDDM2_0DDI_CHECK_VIDEO_PROCESSOR_FORMAT_CONVERSION
title: D3DWDDM2_0DDI_CHECK_VIDEO_PROCESSOR_FORMAT_CONVERSION (d3d10umddi.h)
description: D3DWDDM2_0DDI_CHECK_VIDEO_PROCESSOR_FORMAT_CONVERSION is used with CheckVideoProcessorFormatConversion to indicate whether the driver supports a specific format/color space conversion combination.
old-location: display\d3dwddm2_0ddi_check_video_processor_format_conversion.htm
ms.assetid: 3259CEB7-E902-4040-B99E-D0609935E804
ms.date: 05/10/2018
keywords: ["D3DWDDM2_0DDI_CHECK_VIDEO_PROCESSOR_FORMAT_CONVERSION structure"]
ms.keywords: D3DWDDM2_0DDI_CHECK_VIDEO_PROCESSOR_FORMAT_CONVERSION, D3DWDDM2_0DDI_CHECK_VIDEO_PROCESSOR_FORMAT_CONVERSION structure [Display Devices], d3d10umddi/D3DWDDM2_0DDI_CHECK_VIDEO_PROCESSOR_FORMAT_CONVERSION, display.d3dwddm2_0ddi_check_video_processor_format_conversion
req.header: d3d10umddi.h
req.include-header: D3d10umddi.h
req.target-type: Windows
req.target-min-winverclnt: Windows 10
req.target-min-winversvr: Windows Server 2016
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
req.typenames: D3DWDDM2_0DDI_CHECK_VIDEO_PROCESSOR_FORMAT_CONVERSION
f1_keywords:
 - D3DWDDM2_0DDI_CHECK_VIDEO_PROCESSOR_FORMAT_CONVERSION
 - d3d10umddi/D3DWDDM2_0DDI_CHECK_VIDEO_PROCESSOR_FORMAT_CONVERSION
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - D3d10umddi.h
api_name:
 - D3DWDDM2_0DDI_CHECK_VIDEO_PROCESSOR_FORMAT_CONVERSION
---

# D3DWDDM2_0DDI_CHECK_VIDEO_PROCESSOR_FORMAT_CONVERSION structure


## -description

<b>D3DWDDM2_0DDI_CHECK_VIDEO_PROCESSOR_FORMAT_CONVERSION</b> is used with <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3dwddm2_0ddi_checkvideoprocessorformatconversion">CheckVideoProcessorFormatConversion</a> to indicate whether the driver supports a specific format/color space conversion combination.

## -struct-fields

### -field InputFormat

Indicates the format of the video processor input.

### -field InputColorSpace

Indicates the color space of the video processor input.

### -field OutputFormat

Indicates the format of the video processor output.

### -field OutputColorSpace

Indicates the color space of the video processor output.

### -field Supported

The driver sets this to <b>TRUE</b> if the conversion between the input format/color space and the output format/color space is supported.

## -see-also

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3dwddm2_0ddi_checkvideoprocessorformatconversion">CheckVideoProcessorFormatConversion</a>

