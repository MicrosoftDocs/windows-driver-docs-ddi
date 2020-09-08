---
UID: NS:d3d12umddi.D3D12DDI_VIDEO_PROCESS_OUTPUT_STREAM_0020
title: D3D12DDI_VIDEO_PROCESS_OUTPUT_STREAM_0020 (d3d12umddi.h)
description: The output stream for video processing commands, which points to a target surface.
old-location: display\d3d12ddi_video_process_output_stream.htm
ms.assetid: D6C510B3-D578-41D0-9D52-131F2B61161D
ms.date: 05/10/2018
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

The subresource indexes to use with the associated <b>hDrvTexture2D</b> member.

