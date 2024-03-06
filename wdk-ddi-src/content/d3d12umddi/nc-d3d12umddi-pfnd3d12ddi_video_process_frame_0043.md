---
UID: NC:d3d12umddi.PFND3D12DDI_VIDEO_PROCESS_FRAME_0043
title: PFND3D12DDI_VIDEO_PROCESS_FRAME_0043 (d3d12umddi.h)
description: Implemented by the client driver to process a video frame.
ms.date: 12/14/2023
keywords: ["PFND3D12DDI_VIDEO_PROCESS_FRAME_0043 callback function"]
req.header: d3d12umddi.h
req.include-header: 
req.target-type: 
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.lib: 
req.dll: 
req.irql: 
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
targetos: Windows
tech.root: display
f1_keywords:
 - PFND3D12DDI_VIDEO_PROCESS_FRAME_0043
 - d3d12umddi/PFND3D12DDI_VIDEO_PROCESS_FRAME_0043
topic_type:
 - apiref
api_type:
 - UserDefined
api_location:
 - d3d12umddi.h
api_name:
 - PFND3D12DDI_VIDEO_PROCESS_FRAME_0043
---

# PFND3D12DDI_VIDEO_PROCESS_FRAME_0043 callback function


## -description

The **PFND3D12DDI_VIDEO_PROCESS_FRAME_0043** callback function performs a video processing operation on one or more input samples and writes the result to an output surface.

## -parameters

### -param hDrvCommandList

A handle to the driver's data for the command list. The driver uses this region of memory to store internal data structures that are related to its command list.

### -param hDrvVideoProcessor

The video processor instance to use for this video process call.

### -param pOutputParameters

A [**D3D12DDIARG_VIDEO_PROCESS_OUTPUT_STREAM_ARGUMENTS_0032**](ns-d3d12umddi-d3d12ddiarg_video_process_output_stream_arguments_0032.md) structure to hold the output arguments for the video process.

### -param pInputStreamParameters

A [**D3D12DDIARG_VIDEO_PROCESS_INPUT_STREAM_ARGUMENTS_0043**](ns-d3d12umddi-d3d12ddiarg_video_process_input_stream_arguments_0043.md) structure with the input arguments for the video process.

### -param NumInputStreams

The number of input streams.
