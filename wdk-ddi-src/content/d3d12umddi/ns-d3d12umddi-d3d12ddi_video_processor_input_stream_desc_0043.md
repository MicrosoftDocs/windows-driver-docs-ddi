---
UID: NS:d3d12umddi.D3D12DDI_VIDEO_PROCESSOR_INPUT_STREAM_DESC_0043
title: D3D12DDI_VIDEO_PROCESSOR_INPUT_STREAM_DESC_0043
author: windows-driver-content
description:
ms.assetid: 1fd5caf8-76e9-41a2-9aaf-6bcb3943e1cc
ms.author: windowsdriverdev
ms.date:
ms.topic: struct
ms.prod: windows-hardware
ms.technology: windows-devices
ms.keywords: D3D12DDI_VIDEO_PROCESSOR_INPUT_STREAM_DESC_0043, D3D12DDI_VIDEO_PROCESSOR_INPUT_STREAM_DESC_0043,
req.header: d3d12umddi.h
req.include-header:
req.target-type:
req.target-min-winverclnt:
req.target-min-winversvr:
req.kmdf-ver:
req.umdf-ver:
req.lib:
req.dll:
req.ddi-compliance:
req.unicode-ansi:
req.max-support:
req.typenames: D3D12DDI_VIDEO_PROCESSOR_INPUT_STREAM_DESC_0043
topic_type:
-	apiref
api_type:
-	HeaderDef
api_location:
-	d3d12umddi.h
api_name:
-	D3D12DDI_VIDEO_PROCESSOR_INPUT_STREAM_DESC_0043
product: 
- Windows
targetos: Windows
tech.root: display
---

# D3D12DDI_VIDEO_PROCESSOR_INPUT_STREAM_DESC_0043 structure

## -description

Describes input stream properties for the video processor.

## -struct-fields

### -field Format

The DXGI format of the input texture and references.


### -field ColorSpace

A DXGI_COLOR_SPACE_TYPE value that specifies the colorspace for the video processor input and reference surfaces.


### -field SourceAspectRatio

The source aspect ratio.


### -field DestinationAspectRatio

The destination aspect ratio.


### -field FrameRate

The frame rate of the input video stream, specified as a DXGI_RATIONAL structure.


### -field SourceSizeRange

Describes the minimum and maximum source rectangle size. Video processor should allocate to handle all cases within the range.


### -field DestinationSizeRange

Describes the minimum and maximum destination rectangle size. Video processor should allocate to handle all cases within the range.

### -field EnableOrientation

Enable all transforms specified in D3D12DDI_VIDEO_PROCESS_ORIENTATION.


### -field FilterFlags

A bitwise OR of one or more flags from the D3D12DDI_VIDEO_PROCESS_FILTER_FLAGS_0020 enumeration specifies the filters to enable.


### -field StereoFormat

Uses D3D12DDI_VIDEO_FRAME_STEREO_FORMAT_0020 to specify whether the stream is stereo or not. If the value is D3D12DDI_VIDEO_FRAME_STEREO_FORMAT_SEPARATE, there are two sets of input textures and references (for the stereo interlaced case).

### -field DeinterlaceMode

A D3D12DDI_VIDEO_PROCESS_DEINTERLACE_FLAGS_0020 that represents the deinterlace mode to use.


### -field EnableAlphaBlending

The planar alpha for an input stream on the video processor.  See D3D12DDI_VIDEO_PROCESS_ALPHA_BLENDING.


### -field LumaKey

A D3D12DDI_VIDEO_PROCESS_LUMA_KEY_0020 that represents a luma key for an input stream on the video processor.


### -field NumPastFrames

The number of past frames.


### -field NumFutureFrames

The number of future frames.


### -field EnableAutoProcessing

Enables or disables automatic processing features on the video processor.



