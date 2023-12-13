---
UID: NS:d3d12umddi.D3D12DDIARG_VIDEO_PROCESS_OUTPUT_STREAM_ARGUMENTS_0032
title: D3D12DDIARG_VIDEO_PROCESS_OUTPUT_STREAM_ARGUMENTS_0032 (d3d12umddi.h)
description: Learn more about the D3D12DDIARG_VIDEO_PROCESS_OUTPUT_STREAM_ARGUMENTS_0032 structure.
ms.date: 12/08/2023
keywords: ["D3D12DDIARG_VIDEO_PROCESS_OUTPUT_STREAM_ARGUMENTS_0032 structure"]
ms.keywords: D3D12DDIARG_VIDEO_PROCESS_OUTPUT_STREAM_ARGUMENTS_0032, D3D12DDIARG_VIDEO_PROCESS_OUTPUT_STREAM_ARGUMENTS_0032 structure [Display Devices], d3d12umddi/D3D12DDIARG_VIDEO_PROCESS_OUTPUT_STREAM_ARGUMENTS_0032, display.d3d12ddiarg-video-process-output-stream-arguments-0032
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
req.typenames: D3D12DDIARG_VIDEO_PROCESS_OUTPUT_STREAM_ARGUMENTS_0032
f1_keywords:
 - D3D12DDIARG_VIDEO_PROCESS_OUTPUT_STREAM_ARGUMENTS_0032
 - d3d12umddi/D3D12DDIARG_VIDEO_PROCESS_OUTPUT_STREAM_ARGUMENTS_0032
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - d3d12umddi.h
api_name:
 - D3D12DDIARG_VIDEO_PROCESS_OUTPUT_STREAM_ARGUMENTS_0032
---

# D3D12DDIARG_VIDEO_PROCESS_OUTPUT_STREAM_ARGUMENTS_0032 structure

## -description

**D3D12DDIARG_VIDEO_PROCESS_OUTPUT_STREAM_ARGUMENTS_0032** specifies output stream parameters for the output to be processed by [**PFND3D12DDI_VIDEO_PROCESS_FRAME_0043**](nc-d3d12umddi-pfnd3d12ddi_video_process_frame_0043.md).

## -struct-fields

### -field OutputStream

An array of [**D3D12DDI_VIDEO_PROCESS_OUTPUT_STREAM_0020**](ns-d3d12umddi-d3d12ddi_video_process_output_stream_0020.md) structures that describe the output surfaces for the video process command. If stereo output is enabled, index zero contains the left output while index 1 contains the right input. If stereo output is not enabled, only index 0 is used to specify the output while index 1 should be set to nullptr.

### -field TargetRectangle

A [**D3DDDI_RECT**](/windows/win32/direct3d12/d3d12-rect) structure with the target rectangle, which is the area within the destination surface where the output will be drawn. The target rectangle is given in pixel coordinates, relative to the destination surface.

## -see-also

[**PFND3D12DDI_VIDEO_PROCESS_FRAME_0043**](nc-d3d12umddi-pfnd3d12ddi_video_process_frame_0043.md)
