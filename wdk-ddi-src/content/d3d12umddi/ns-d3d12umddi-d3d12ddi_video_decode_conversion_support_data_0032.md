---
UID: NS:d3d12umddi.D3D12DDI_VIDEO_DECODE_CONVERSION_SUPPORT_DATA_0032
title: D3D12DDI_VIDEO_DECODE_CONVERSION_SUPPORT_DATA_0032
author: windows-driver-content
description: Video decode conversion support data.
old-location: display\d3d12ddi-video-decode-conversion-support-data-0032.htm
ms.assetid: 1395fe30-9bbf-433c-8696-a0f842bad10e
ms.date: 4/16/2018
ms.keywords: D3D12DDI_VIDEO_DECODE_CONVERSION_SUPPORT_DATA_0032, D3D12DDI_VIDEO_DECODE_CONVERSION_SUPPORT_DATA_0032 structure [Display Devices], d3d12umddi/D3D12DDI_VIDEO_DECODE_CONVERSION_SUPPORT_DATA_0032, display.d3d12ddi-video-decode-conversion-support-data-0032
ms.topic: struct
req.header: d3d12umddi.h
req.include-header:
req.target-type: Windows
req.target-min-winverclnt:
req.target-min-winversvr:
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
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	d3d12umddi.h
api_name:
-	D3D12DDI_VIDEO_DECODE_CONVERSION_SUPPORT_DATA_0032
product:
- Windows
targetos: Windows
tech.root: display
req.typenames: D3D12DDI_VIDEO_DECODE_CONVERSION_SUPPORT_DATA_0032
---

# D3D12DDI_VIDEO_DECODE_CONVERSION_SUPPORT_DATA_0032 structure


## -description


Structure used to check if a color space conversion, format conversion, and scale are supported, and whether it is required for real-time reasons or reference buffer format.


## -struct-fields




### -field NodeIndex

In multi-adapter operation, the NodeIndex indicates which physical adapter of the device this operation applies to.


### -field Configuration

The decode profile and bitstream encryption. See [D3D12DDI_VIDEO_DECODE_CONFIGURATION](ns-d3d12umddi-d3d12ddi_video_decode_configuration_0020.md).


### -field DecodeSample

The source decoded as sample description. See [D3D12DDI_VIDEO_SAMPLE_DESCRIPTION](ns-d3d12umddi-d3d12ddi_video_sample_description_0020.md).


### -field OutputFormat

The output sample description. See [D3D12DDI_VIDEO_FORMAT_DESCRIPTION](ns-d3d12umddi-d3d12ddi_video_format_description_0020.md).


### -field FrameRate

The frame rate of the video content. This is used by the driver to determine whether the video can be decoded in real-time.


### -field BitRate

The average bits per second data compression rate for the compressed video stream. This is used by the driver to determine whether the video can be decoded in real-time.


### -field SupportFlags

Supported flags. See [D3D12DDI_VIDEO_DECODE_CONVERSION_SUPPORT_FLAGS](ne-d3d12umddi-d3d12ddi_video_decode_conversion_support_flags_0020.md).


### -field ScaleSupport

Indicates the supported output size range for decode conversion. See [D3D12DDI_VIDEO_SCALE_SUPPORT](ns-d3d12umddi-d3d12ddi_video_scale_support_0032.md).


## -remarks

If the color space and format conversion is reported, **SupportedFlags** will have D3D12DDI_VIDEO_DECODE_SUPPORT_FLAGS_SUPPORTED set. Callers should check **ScaleSupport** to understand if the scale is supported.


## -see-also

[D3D12DDI_VIDEO_DECODE_CONVERSION_SUPPORT_FLAGS](ne-d3d12umddi-d3d12ddi_video_decode_conversion_support_flags_0020.md)
