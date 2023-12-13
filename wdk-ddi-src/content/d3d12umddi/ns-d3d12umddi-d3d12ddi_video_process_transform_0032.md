---
UID: NS:d3d12umddi.D3D12DDI_VIDEO_PROCESS_TRANSFORM_0032
title: D3D12DDI_VIDEO_PROCESS_TRANSFORM_0032 (d3d12umddi.h)
description: Learn more about the D3D12DDI_VIDEO_PROCESS_TRANSFORM_0032 structure.
ms.date: 12/12/2023
keywords: ["D3D12DDI_VIDEO_PROCESS_TRANSFORM_0032 structure"]
ms.keywords: D3D12DDI_VIDEO_PROCESS_TRANSFORM_0032, D3D12DDI_VIDEO_PROCESS_TRANSFORM_0032 structure [Display Devices], d3d12umddi/D3D12DDI_VIDEO_PROCESS_TRANSFORM_0032, display.d3d12ddi-video-process-transform-0032
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
req.typenames: D3D12DDI_VIDEO_PROCESS_TRANSFORM_0032
f1_keywords:
 - D3D12DDI_VIDEO_PROCESS_TRANSFORM_0032
 - d3d12umddi/D3D12DDI_VIDEO_PROCESS_TRANSFORM_0032
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - d3d12umddi.h
api_name:
 - D3D12DDI_VIDEO_PROCESS_TRANSFORM_0032
---

# D3D12DDI_VIDEO_PROCESS_TRANSFORM_0032 structure

## -description

The **D3D12DDI_VIDEO_PROCESS_TRANSFORM_0032** structure specifies the flip, rotation, scale, and destination translation for the video input.

## -struct-fields

### -field SourceRectangle

The source rectangle is the portion of the input surface that is bltted (bit block transferred) to the destination surface. The source rectangle is given in pixel coordinates, relative to the input surface. Stereo format after orientation is applied.

### -field DestinationRectangle

The destination rectangle is the portion of the output surface that receives the blt for this stream. The destination rectangle is given in pixel coordinates, relative to the output surface.

### -field Orientation

A [**D3D12DDI_VIDEO_PROCESS_ORIENTATION_0020**](ne-d3d12umddi-d3d12ddi_video_process_orientation_0020.md) value that specifies the rotation and flip operation to apply to the source. Source and Destination rectangles are specified in post orientation coordinates.

## -see-also

[**D3D12DDIARG_VIDEO_PROCESS_INPUT_STREAM_ARGUMENTS_0043**](ns-d3d12umddi-d3d12ddiarg_video_process_input_stream_arguments_0043.md)
