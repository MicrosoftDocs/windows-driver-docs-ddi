---
UID: NS:d3d12umddi.D3D12DDI_VIDEO_PROCESS_OUTPUT_STREAM_0020
title: D3D12DDI_VIDEO_PROCESS_OUTPUT_STREAM_0020
author: windows-driver-content
description: The output stream for video processing commands, which points to a target surface.
old-location: display\d3d12ddi_video_process_output_stream.htm
old-project: display
ms.assetid: D6C510B3-D578-41D0-9D52-131F2B61161D
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: D3D12DDI_VIDEO_PROCESS_OUTPUT_STREAM_0020, D3D12DDI_VIDEO_PROCESS_OUTPUT_STREAM_0020
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: d3d12umddi.h
req.include-header: D3d12umddi.h
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: D3D12DDI_VIDEO_PROCESS_OUTPUT_STREAM_0020
req.alt-loc: D3d12umddi.h
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
req.typenames: D3D12DDI_VIDEO_PROCESS_OUTPUT_STREAM_0020
---

# D3D12DDI_VIDEO_PROCESS_OUTPUT_STREAM_0020 structure



## -description
The output stream for video processing commands, which points to a target surface.



## -syntax

````
typedef struct D3D12DDI_VIDEO_PROCESS_OUTPUT_STREAM_0020 {
  D3D12DDI_HRESOURCE hDrvTexture2D;
  UINT               Subresource;
} D3D12DDI_VIDEO_PROCESS_OUTPUT_STREAM_0020;
````


## -struct-fields

### -field hDrvTexture2D

The output surfaces for the video process command.  


### -field Subresource

The subresource indexes to use with the associated <b>hDrvTexture2D</b> member.


## -remarks
