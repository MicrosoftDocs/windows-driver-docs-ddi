---
UID: NS:d3d12umddi.D3D12DDI_VIDEO_DECODE_CONVERSION_SUPPORT_DATA_0022
title: D3D12DDI_VIDEO_DECODE_CONVERSION_SUPPORT_DATA_0022 (d3d12umddi.h)
description: Specifies information used to check whether a color space conversion, format conversion, and scale are supported and whether it is required for real-time reasons or reference buffer format.
old-location: display\d3d12ddi_video_decode_conversion_support_data.htm
ms.date: 05/10/2018
keywords: ["D3D12DDI_VIDEO_DECODE_CONVERSION_SUPPORT_DATA_0022 structure"]
ms.keywords: D3D12DDI_VIDEO_DECODE_CONVERSION_SUPPORT_DATA_0022, D3D12DDI_VIDEO_DECODE_CONVERSION_SUPPORT_DATA_0022 structure [Display Devices], d3d12umddi/D3D12DDI_VIDEO_DECODE_CONVERSION_SUPPORT_DATA_0022, display.d3d12ddi_video_decode_conversion_support_data
f1_keywords:
 - "d3d12umddi/D3D12DDI_VIDEO_DECODE_CONVERSION_SUPPORT_DATA_0022"
 - "D3D12DDI_VIDEO_DECODE_CONVERSION_SUPPORT_DATA_0022"
req.header: d3d12umddi.h
req.include-header: D3d12umddi.h
req.target-type: Windows
req.target-min-winverclnt:
req.target-min-winversvr:
req.kmdf-ver:
req.umdf-ver:
req.ddi-compliance:
req.unicode-ansi:
req.idl:
req.max-support: Windows 10, version 1709
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
- D3d12umddi.h
api_name:
- D3D12DDI_VIDEO_DECODE_CONVERSION_SUPPORT_DATA_0022
targetos: Windows
tech.root: display
req.typenames: D3D12DDI_VIDEO_DECODE_CONVERSION_SUPPORT_DATA_0022
---

# D3D12DDI_VIDEO_DECODE_CONVERSION_SUPPORT_DATA_0022 structure


## -description


Specifies information used to check whether a color space conversion, format conversion, and scale are supported and whether it is required for real-time reasons or reference buffer format.


## -struct-fields




### -field NodeIndex

In multi-adapter operation, this indicates which physical adapter of the device this operation applies to.


### -field Configuration

The decode profile and bitstream encryption.  For more information, see the  <a href="/windows-hardware/drivers/ddi/d3d12umddi/ne-d3d12umddi-d3d12ddi_video_decode_configuration_flags_0020">D3D12DDI_VIDEO_DECODE_CONFIGURATION</a> enumeration.


### -field DecodeSample

The source decoded as sample description.  For more information, see the  <a href="/windows-hardware/drivers/ddi/d3d12umddi/ns-d3d12umddi-d3d12ddi_video_sample_description_0020">D3D12DDI_VIDEO_SAMPLE_DESCRIPTION</a> structure.


### -field OutputFormat

The output sample description.  For more information, see the  <a href="/windows-hardware/drivers/ddi/d3d12umddi/ns-d3d12umddi-d3d12ddi_video_format_description_0020">D3D12DDI_VIDEO_FORMAT_DESCRIPTION</a> structure.


### -field FrameRate

The frame rate of the video content. This is used by the driver to determine whether the video can be decoded in real time.


### -field BitRate

The average bits per second data compression rate for the compressed video stream.  This is used by the driver to determine whether the video can be decoded in real time.


### -field SupportFlags

The returned supported flags. For more information, see the <a href="/windows-hardware/drivers/ddi/d3d12umddi/ne-d3d12umddi-d3d12ddi_video_decode_conversion_support_flags_0020">D3D12DDI_VIDEO_DECODE_CONVERSION_SUPPORT_FLAGS</a> enumeration.


### -field ScaleSupport

The returned supported output size range for decode conversion.  For more information, see the <a href="/previous-versions/mt782353(v=vs.85)">D3D12DDI_VIDEO_SCALE_SUPPORT</a> structure.


## -remarks



The check is made through <a href="/windows-hardware/drivers/ddi/d3d12umddi/nc-d3d12umddi-pfnd3d12ddi_video_getcaps">pfnGetCaps</a> with the <a href="/windows-hardware/drivers/ddi/d3d12umddi/ne-d3d12umddi-d3d12ddicaps_type">D3D12DDICAPS_TYPE</a> set to a value of <b>D3D12DDICAPS_TYPE_VIDEO_DECODE_CONVERSION_SUPPORT</b>.

If the color space and format conversion is reported, the <i>SupportedFlags</i> has the <b>D3D12DDI_VIDEO_DECODE_SUPPORT_FLAGS_SUPPORTED</b> flag set.

Callers should check the <i>ScaleSupport</i> parameter to understand if the scale is supported.




## -see-also




<a href="/windows-hardware/drivers/ddi/d3d12umddi/ne-d3d12umddi-d3d12ddicaps_type">D3D12DDICAPS_TYPE</a>



<a href="/windows-hardware/drivers/ddi/d3d12umddi/ne-d3d12umddi-d3d12ddi_video_decode_configuration_flags_0020">D3D12DDI_VIDEO_DECODE_CONFIGURATION</a>



<a href="/windows-hardware/drivers/ddi/d3d12umddi/ne-d3d12umddi-d3d12ddi_video_decode_conversion_support_flags_0020">D3D12DDI_VIDEO_DECODE_CONVERSION_SUPPORT_FLAGS</a>



<a href="/windows-hardware/drivers/ddi/d3d12umddi/ns-d3d12umddi-d3d12ddi_video_format_description_0020">D3D12DDI_VIDEO_FORMAT_DESCRIPTION</a>



<a href="/windows-hardware/drivers/ddi/d3d12umddi/ns-d3d12umddi-d3d12ddi_video_sample_description_0020">D3D12DDI_VIDEO_SAMPLE_DESCRIPTION</a>



<a href="/previous-versions/mt782353(v=vs.85)">D3D12DDI_VIDEO_SCALE_SUPPORT</a>
 

 
