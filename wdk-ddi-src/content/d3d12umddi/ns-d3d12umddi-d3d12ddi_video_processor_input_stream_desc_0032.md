---
UID: NS:d3d12umddi.D3D12DDI_VIDEO_PROCESSOR_INPUT_STREAM_DESC_0032
title: D3D12DDI_VIDEO_PROCESSOR_INPUT_STREAM_DESC_0032
author: windows-driver-content
description: Describes input stream properties for the video processor.
old-location: display\d3d12ddi_video_processor_input_stream_desc_0032.htm
old-project: display
ms.assetid: 3A4D19FD-FC65-4B78-8F0E-9792EB0A9B03
ms.author: windowsdriverdev
ms.date: 2/24/2018
ms.keywords: D3D12DDI_VIDEO_PROCESSOR_INPUT_STREAM_DESC_0032, D3D12DDI_VIDEO_PROCESSOR_INPUT_STREAM_DESC_0032 structure [Display Devices], d3d12umddi/D3D12DDI_VIDEO_PROCESSOR_INPUT_STREAM_DESC_0032, display.d3d12ddi_video_processor_input_stream_desc_0032
ms.prod: windows-hardware
ms.technology: windows-devices
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
-	D3D12DDI_VIDEO_PROCESSOR_INPUT_STREAM_DESC_0032
product: Windows
targetos: Windows
req.typenames: D3D12DDI_VIDEO_PROCESSOR_INPUT_STREAM_DESC_0032
---

# D3D12DDI_VIDEO_PROCESSOR_INPUT_STREAM_DESC_0032 structure


## -description


Describes input stream properties for the video processor.


## -syntax


````
typedef struct _D3D12DDI_VIDEO_PROCESSOR_INPUT_STREAM_DESC_0032 {
  DXGI_FORMAT                                Format;
  DXGI_COLOR_SPACE_TYPE                      ColorSpace;
  DXGI_RATIONAL                              SourceAspectRatio;
  DXGI_RATIONAL                              DestinationAspectRatio;
  DXGI_RATIONAL                              FrameRate;
  D3D12DDI_VIDEO_SIZE_RANGE                  SourceSizeRange;
  D3D12DDI_VIDEO_SIZE_RANGE                  DestinationSizeRanges;
  BOOL                                       EnableOrientation;
  D3D12DDI_VIDEO_PROCESS_ALPHA_BLENDING_0020 FilterFlags;
  D3D12DDI_VIDEO_PROCESS_FILTER_FLAGS_0020   StereoFormat;
  D3D12DDI_VIDEO_FIELD_TYPE_0020             FieldType;
  D3D12DDI_VIDEO_FRAME_STEREO_FORMAT_0020    DeinterlaceMode;
  BOOL                                       EnableAlphaBlending;
  D3D12DDI_VIDEO_PROCESS_LUMA_KEY_0020       LumaKey;
  UINT                                       NumPastFrames;
  UINT                                       NumFutureFrames;
  BOOL                                       EnableAutoProcessing;
} D3D12DDI_VIDEO_PROCESSOR_INPUT_STREAM_DESC_0032;
````


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

Describes the minimum and maximum source rectangle size.  Video processor should allocate to handle all cases within the range.


### -field DestinationSizeRange

 


### -field EnableOrientation

Enable all transforms specified in D3D12DDI_VIDEO_PROCESS_ORIENTATION.


### -field FilterFlags

A bitwise OR of one or more flags from the D3D12DDI_VIDEO_PROCESS_FILTER_FLAGS enumeration specifies the filters to enable.


### -field StereoFormat

Specifies whether the stream is stereo or not. If D3D12DDI_VIDEO_FRAME_STEREO_FORMAT_SEPARATE, we have two sets of input textures and references (for the stereo interlaced case).


### -field FieldType

Specifies the frame format as progressive or interlaced for the input stream.  See D3D12DDI_VIDEO_FIELD_TYPE.


### -field DeinterlaceMode

The deinterlace mode to use.  See D3D12DDI_VIDEO_PROCESS_DEINTERLACE_FLAGS.


### -field EnableAlphaBlending

The planar alpha for an input stream on the video processor.  See D3D12DDI_VIDEO_PROCESS_ALPHA_BLENDING.


### -field LumaKey

The luma key for an input stream on the video processor.  See D3D12DDI_VIDEO_PROCESS_LUMA_KEY for more details.


### -field NumPastFrames

The number of past frames.


### -field NumFutureFrames

The number of future frames.


### -field EnableAutoProcessing

Enables or disables automatic processing features on the video processor.


#### - DestinationSizeRanges

Describes the minimum and maximum destination rectangle size.  Video processor should allocate to handle all cases within the range.

