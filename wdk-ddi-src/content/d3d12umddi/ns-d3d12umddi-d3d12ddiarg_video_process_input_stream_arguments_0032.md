---
UID: NS:d3d12umddi.D3D12DDIARG_VIDEO_PROCESS_INPUT_STREAM_ARGUMENTS_0032
title: D3D12DDIARG_VIDEO_PROCESS_INPUT_STREAM_ARGUMENTS_0032 (d3d12umddi.h)
description: The video process input stream arguments.
old-location: display\d3d12ddiarg-video-process-input-stream-arguments-0032.htm
ms.assetid: b6eafa0c-1b5e-4723-9317-60f1507f12ea
ms.date: 04/16/2018
ms.keywords: D3D12DDIARG_VIDEO_PROCESS_INPUT_STREAM_ARGUMENTS_0032, D3D12DDIARG_VIDEO_PROCESS_INPUT_STREAM_ARGUMENTS_0032 structure [Display Devices], d3d12umddi/D3D12DDIARG_VIDEO_PROCESS_INPUT_STREAM_ARGUMENTS_0032, display.d3d12ddiarg-video-process-input-stream-arguments-0032
f1_keywords:
 - "d3d12umddi/D3D12DDIARG_VIDEO_PROCESS_INPUT_STREAM_ARGUMENTS_0032"
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
- D3D12DDIARG_VIDEO_PROCESS_INPUT_STREAM_ARGUMENTS_0032
product:
- Windows
targetos: Windows
tech.root: display
req.typenames: D3D12DDIARG_VIDEO_PROCESS_INPUT_STREAM_ARGUMENTS_0032
---

# D3D12DDIARG_VIDEO_PROCESS_INPUT_STREAM_ARGUMENTS_0032 structure


## -description


Specifies input stream parameters for an input stream passed to [PFND3D12DDI_VIDEO_PROCESS_FRAME](nc-d3d12umddi-pfnd3d12ddi_video_process_frame_0032.md).


## -struct-fields




### -field InputStream

Contains the set of references to be able to perform processing. If stereo format is [D3D12DDI_VIDEO_FRAME_STEREO_FORMAT_SEPARATE](ne-d3d12umddi-d3d12ddi_video_frame_stereo_format_0020.md), then two sets of input streams must be supplied. If stereo format is any other mode, the first set of reference must be supplied, and the second should be zero initialized.


### -field Transform

Specifies flip, rotation, scale and destination translation for the video input. See [D3D12DDI_VIDEO_PROCESS_TRANSFORM](ns-d3d12umddi-d3d12ddi_video_process_transform_0032.md).


### -field Flags

Specifies options for the input stream. See [D3D12DDI_VIDEO_PROCESS_INPUT_STREAM_FLAGS](ne-d3d12umddi-d3d12ddi_video_process_input_stream_flags_0020.md).


### -field RateInfo

Specifies frame rate and input and output indices for framerate conversion and deinterlacing.  See [D3D12DDI_VIDEO_PROCESS_INPUT_STREAM_RATE_INFO](ns-d3d12umddi-d3d12ddi_video_process_input_stream_rate_info_0032.md).


### -field FilterLevels

The level to apply for each enabled filter. Filter level is specified in the order that filters appear in the [D3D12DDI_VIDEO_PROCESS_FILTER_FLAGS](ne-d3d12umddi-d3d12ddi_video_process_filter_flags_0020.md). Specify 0 if a filter is not enabled or the filter index is reserved.


### -field AlphaBlending

The planar alpha for an input stream on the video processor. See [D3D12DDI_VIDEO_PROCESS_ALPHA_BLENDING](ns-d3d12umddi-d3d12ddi_video_process_alpha_blending_0020.md).

## -remarks

The size of the video decoder heap is static at compile time.
