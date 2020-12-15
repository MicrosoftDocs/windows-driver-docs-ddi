---
UID: NC:d3d12umddi.PFND3D12DDI_VIDEO_DECODE_FRAME_0032
title: PFND3D12DDI_VIDEO_DECODE_FRAME_0032 (d3d12umddi.h)
description: Used to decode a video frame.
old-location: display\pfnd3d12ddi_video_decode_frame_0032.htm
ms.date: 03/29/2018
keywords: ["PFND3D12DDI_VIDEO_DECODE_FRAME_0032 callback"]
ms.keywords: PFND3D12DDI_VIDEO_DECODE_FRAME_0030, PFND3D12DDI_VIDEO_DECODE_FRAME_0030 callback function [Display Devices], d3d12umddi/PFND3D12DDI_VIDEO_DECODE_FRAME_0030, display.pfnd3d12ddi_video_decode_frame_0032
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
targetos: Windows
tech.root: display
req.typenames: D3D11_1DDI_GETCAPTUREHANDLEDATA
f1_keywords:
 - PFND3D12DDI_VIDEO_DECODE_FRAME_0032
 - d3d12umddi/PFND3D12DDI_VIDEO_DECODE_FRAME_0032
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - d3d12umddi.h
api_name:
 - PFND3D12DDI_VIDEO_DECODE_FRAME_0030
product:
 - Windows
---

# PFND3D12DDI_VIDEO_DECODE_FRAME_0032 callback


## -description

Records a decode frame operation to the command list.  Inputs, outputs, and parameters for the decode are specified as arguments to this method.

## -parameters

### -param hDrvCommandList

A handle to the driver's data for the command list. The driver uses this region of memory to store internal data structures that are related to its command list.

### -param hDrvDecoder

The video decoder that contains internal state for this decode session.  Examples include motion vectors, internal temporary allocations, etc.  See [Creating a Video Decoder](/windows-hardware/drivers/display/creating-a-video-decode-device).

### -param pOutputStreamParameters

Specifies the output surface and output parameters. See [D3D12DDI_VIDEO_DECODE_OUTPUT_STREAM_ARGUMENTS](ns-d3d12umddi-d3d12ddi_video_decode_output_stream_arguments_0021.md).

### -param pInputStreamParameters

Specifies the input bit stream, parameters, reference frames, and other input parameters for the decode operation.  See [D3D12DDI_VIDEO_DECODE_INPUT_STREAM_ARGUMENTS](ns-d3d12umddi-d3d12ddi_video_decode_input_stream_arguments_0032.md).
