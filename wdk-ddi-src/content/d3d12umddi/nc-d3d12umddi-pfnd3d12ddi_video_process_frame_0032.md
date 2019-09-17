---
UID: NC:d3d12umddi.PFND3D12DDI_VIDEO_PROCESS_FRAME_0032
title: PFND3D12DDI_VIDEO_PROCESS_FRAME_0032 (d3d12umddi.h)
description: Used to process a video frame.
old-location: display\pfnd3d12ddi_video_process_frame_0032.htm
ms.assetid: C7923B09-FBA2-43EE-A56B-0B8B6C3403A0
ms.date: 04/16/2018
ms.keywords: PFND3D12DDI_VIDEO_PROCESS_FRAME_0032, PFND3D12DDI_VIDEO_PROCESS_FRAME_0032 callback, PFND3D12DDI_VIDEO_PROCESS_FRAME_0032 callback function [Display Devices], d3d12umddi/PFND3D12DDI_VIDEO_PROCESS_FRAME_0032, display.pfnd3d12ddi_video_process_frame_0032
ms.topic: callback
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
req.typenames: 
f1_keywords:
 - "d3d12umddi/PFND3D12DDI_VIDEO_PROCESS_FRAME_0032"
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - d3d12umddi.h
api_name:
 - PFND3D12DDI_VIDEO_PROCESS_FRAME_0032
product:
 - Windows
---

# PFND3D12DDI_VIDEO_PROCESS_FRAME_0032 callback function

## -description

Performs a video processing operation on one or more input samples and writes the result to an output surface

## -parameters

### -param hDrvCommandList

The command list used to record this process frames command.

### -param hDrvVideoProcessor

The video processor instance to use for this video process call. The video processor holds state for a video processing session, including required intermediate memory, cached processing data, or other temporary working space.

### -param pOutputParameters

The output arguments for the video process. The available parameters are in the [D3D12DDIARG_VIDEO_PROCESS_OUTPUT_STREAM_ARGUMENTS](ns-d3d12umddi-d3d12ddiarg_video_process_output_stream_arguments_0032.md) structure.

### -param pInputStreamParameters

Specifies an array of input parameters. The available parameters are in the [D3D12DDIARG_VIDEO_PROCESS_INPUT_STREAM_ARGUMENTS](ns-d3d12umddi-d3d12ddiarg_video_process_input_stream_arguments_0032.md) structure.

### -param NumInputStreams

The count of input streams.

## -returns

This callback function does not return a value.

