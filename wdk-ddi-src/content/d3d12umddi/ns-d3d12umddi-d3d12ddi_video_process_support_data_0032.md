---
UID: NS:d3d12umddi.D3D12DDI_VIDEO_PROCESS_SUPPORT_DATA_0032
title: D3D12DDI_VIDEO_PROCESS_SUPPORT_DATA_0032 (d3d12umddi.h)
description: Video process support data.
old-location: display\d3d12ddi-video-process-support-data-0032.htm
ms.assetid: ea2dabc5-6853-4491-8c1f-f3f5ae516952
ms.date: 04/16/2018
ms.keywords: D3D12DDI_VIDEO_PROCESS_SUPPORT_DATA_0032, D3D12DDI_VIDEO_PROCESS_SUPPORT_DATA_0032 structure [Display Devices], d3d12umddi/D3D12DDI_VIDEO_PROCESS_SUPPORT_DATA_0032, display.d3d12ddi-video-process-support-data-0032
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
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- d3d12umddi.h
api_name:
- D3D12DDI_VIDEO_PROCESS_SUPPORT_DATA_0032
product:
- Windows
targetos: Windows
tech.root: display
req.typenames: D3D12DDI_VIDEO_PROCESS_SUPPORT_DATA_0032
---

# D3D12DDI_VIDEO_PROCESS_SUPPORT_DATA_0032 structure


## -description


Structure for the [D3D12DDICAPS_TYPE_VIDEO_PROCESS_SUPPORT](ns-d3d12umddi-d3d12ddi_video_decode_support_data_0020.md) capability check.This structure is used to retrieve the capabilities for the video processor.


## -struct-fields




### -field NodeIndex

In multi-adapter operation, this indicates which physical adapter of the device this operation applies to.


### -field InputSample

Input Width, Height, and Format. See [D3D12DDI_VIDEO_SAMPLE_DESCRIPTION](ns-d3d12umddi-d3d12ddi_video_sample_description_0020.md).


### -field InputFieldType

The interlaced field type of the input sample. See [D3D12DDI_VIDEO_FIELD_TYPE](ne-d3d12umddi-d3d12ddi_video_field_type_0020.md).


### -field InputStereoFormat

The stereo format of the input. See [D3D12DDI_VIDEO_FRAME_STEREO_FORMAT](ne-d3d12umddi-d3d12ddi_video_frame_stereo_format_0020.md).


### -field InputFrameRate

The input frame rate.


### -field OutputFormat

The output DXGI format and color space. See [D3D12DDI_VIDEO_FORMAT_DESCRIPTION](ns-d3d12umddi-d3d12ddi_video_format_description_0020.md).


### -field OutputStereoFormat

The stereo format of the output. See [D3D12DDI_VIDEO_FRAME_STEREO_FORMAT](ne-d3d12umddi-d3d12ddi_video_frame_stereo_format_0020.md).


### -field OutputFrameRate

The frame rate of the output.


### -field SupportFlags

Indicates if the conversion from input format and color space to output format and color space is supported. See [D3D12DDI_VIDEO_PROCESS_SUPPORT_FLAGS](ne-d3d12umddi-d3d12ddi_video_process_support_flags_0022.md) for details,


### -field ScaleSupport

Indicates the supported output scale range for the input to output processing. See [D3D12DDI_VIDEO_SCALE_SUPPORT](ns-d3d12umddi-d3d12ddi_video_scale_support_0032.md).


### -field FeatureSupport

A bitwise OR of zero or more flags from the [D3D12DDI_VIDEO_PROCESS_FEATURE_SUPPORT_FLAGS](ne-d3d12umddi-d3d12ddi_video_process_feature_support_flags_0020.md) enumeration.


### -field DeinterlaceSupport

The deinterlace modes supported by the driver. See [D3D12DDI_VIDEO_PROCESS_DEINTERLACE_FLAGS](ne-d3d12umddi-d3d12ddi_video_process_deinterlace_flags_0020.md).


### -field AutoProcessingSupport

Indicates the type of auto processing operations supported by driver.


### -field FilterSupport

A bitwise OR of zero or more flags from the [D3D12DDI_VIDEO_PROCESS_FILTER_FLAGS](ne-d3d12umddi-d3d12ddi_video_process_filter_flags_0020.md) enumeration.


### -field FilterRangeSupport

The list of filter range values. The order of the range values should be specified in the same order that the filters appear in the D3D12DDI_VIDEO_PROCESS_FILTER_FLAGS. D3D12DDI_VIDEO_PROCESS_MAX_FILTERS range values are available for current and future filters. The D3D runtime will zero initialize any range value that is not supported by the driver.
The value of D3D12DDI_VIDEO_PROCESS_MAX_FILTERS is defined as such:

```c
#define D3D12DDI_VIDEO_PROCESS_MAX_FILTERS_0020 32
```

