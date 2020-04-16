---
UID: NE:d3d12umddi.D3D12DDI_VIDEO_PROCESS_INPUT_STREAM_FLAGS_0020
title: D3D12DDI_VIDEO_PROCESS_INPUT_STREAM_FLAGS_0020 (d3d12umddi.h)
description: Input stream flags.
old-location: display\d3d12ddi_video_process_input_stream_flags.htm
ms.assetid: 6BF1C31E-45F8-4921-87A2-53331530EAC4
ms.date: 05/10/2018
keywords: ["D3D12DDI_VIDEO_PROCESS_INPUT_STREAM_FLAGS_0020 enumeration"]
ms.keywords: D3D12DDI_VIDEO_PROCESS_INPUT_STREAM_FLAGS, D3D12DDI_VIDEO_PROCESS_INPUT_STREAM_FLAGS enumeration [Display Devices], D3D12DDI_VIDEO_PROCESS_INPUT_STREAM_FLAGS_0020, D3D12DDI_VIDEO_PROCESS_INPUT_STREAM_FLAG_0020_FRAME_DISCONTINUITY, D3D12DDI_VIDEO_PROCESS_INPUT_STREAM_FLAG_0020_FRAME_REPEAT, D3D12DDI_VIDEO_PROCESS_INPUT_STREAM_FLAG_0020_NONE, d3d12umddi/D3D12DDI_VIDEO_PROCESS_INPUT_STREAM_FLAGS, d3d12umddi/D3D12DDI_VIDEO_PROCESS_INPUT_STREAM_FLAG_0020_FRAME_DISCONTINUITY, d3d12umddi/D3D12DDI_VIDEO_PROCESS_INPUT_STREAM_FLAG_0020_FRAME_REPEAT, d3d12umddi/D3D12DDI_VIDEO_PROCESS_INPUT_STREAM_FLAG_0020_NONE, display.d3d12ddi_video_process_input_stream_flags
f1_keywords:
 - "d3d12umddi/D3D12DDI_VIDEO_PROCESS_INPUT_STREAM_FLAGS_0020"
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
topic_type:
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- D3d12umddi.h
api_name:
- D3D12DDI_VIDEO_PROCESS_INPUT_STREAM_FLAGS_0020
product:
- Windows
targetos: Windows
tech.root: display
req.typenames: D3D12DDI_VIDEO_PROCESS_INPUT_STREAM_FLAGS_0020
---

# D3D12DDI_VIDEO_PROCESS_INPUT_STREAM_FLAGS_0020 enumeration


## -description


Input stream flags.


## -enum-fields




### -field D3D12DDI_VIDEO_PROCESS_INPUT_STREAM_FLAG_0020_NONE

No flags specified.


### -field D3D12DDI_VIDEO_PROCESS_INPUT_STREAM_FLAG_0020_FRAME_DISCONTINUITY

The application must set this flag when not processing frames in order, such as seeking between frames.  This should be a hint that cached filter processing from previous calls to process frames is invalid.


### -field D3D12DDI_VIDEO_PROCESS_INPUT_STREAM_FLAG_0020_FRAME_REPEAT

The application must set this flag when it applies video process operations to the same set of inputs.  For example, paused video where the window is being resized causing a scale.

