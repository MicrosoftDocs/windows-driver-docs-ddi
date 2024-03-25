---
UID: NS:d3d12umddi.D3D12DDI_VIDEO_PROCESS_OUTPUT_STREAM_0020
title: D3D12DDI_VIDEO_PROCESS_OUTPUT_STREAM_0020 (d3d12umddi.h)
description: Learn more about the D3D12DDI_VIDEO_PROCESS_OUTPUT_STREAM_0020 structure.
ms.date: 12/08/2023
keywords: ["D3D12DDI_VIDEO_PROCESS_OUTPUT_STREAM_0020 structure"]
ms.keywords: D3D12DDI_VIDEO_PROCESS_OUTPUT_STREAM_0020, D3D12DDI_VIDEO_PROCESS_OUTPUT_STREAM_0020 structure [Display Devices], d3d12umddi/D3D12DDI_VIDEO_PROCESS_OUTPUT_STREAM_0020, display.d3d12ddi_video_process_output_stream
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
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: 
targetos: Windows
tech.root: display
req.typenames: D3D12DDI_VIDEO_PROCESS_OUTPUT_STREAM_0020
f1_keywords:
 - D3D12DDI_VIDEO_PROCESS_OUTPUT_STREAM_0020
 - d3d12umddi/D3D12DDI_VIDEO_PROCESS_OUTPUT_STREAM_0020
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - D3d12umddi.h
api_name:
 - D3D12DDI_VIDEO_PROCESS_OUTPUT_STREAM_0020
---

# D3D12DDI_VIDEO_PROCESS_OUTPUT_STREAM_0020 structure

## -description

The output stream for video processing commands, which points to a target surface.

## -struct-fields

### -field hDrvTexture2D

The output surfaces for the video process command.

### -field Subresource

The subresource indexes to use with the associated **hDrvTexture2D** member.

## -see-also

[**D3D12DDIARG_VIDEO_PROCESS_OUTPUT_STREAM_ARGUMENTS_0032**](ns-d3d12umddi-d3d12ddiarg_video_process_output_stream_arguments_0032.md)

[**PFND3D12DDI_VIDEO_PROCESS_FRAME_0043**](nc-d3d12umddi-pfnd3d12ddi_video_process_frame_0043.md)
