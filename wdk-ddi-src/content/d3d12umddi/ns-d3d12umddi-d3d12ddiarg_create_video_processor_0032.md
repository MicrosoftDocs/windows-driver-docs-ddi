---
UID: NS:d3d12umddi.D3D12DDIARG_CREATE_VIDEO_PROCESSOR_0032
title: D3D12DDIARG_CREATE_VIDEO_PROCESSOR_0032
author: windows-driver-content
description: Creates a video processor.
old-location: display\d3d12ddiarg-create-video-processor-0032.htm
ms.assetid: 6b945476-c1cf-4bf8-8273-bb3d05b90277
ms.date: 04/16/2018
ms.keywords: D3D12DDIARG_CREATE_VIDEO_PROCESSOR_0032, D3D12DDIARG_CREATE_VIDEO_PROCESSOR_0032 structure [Display Devices], d3d12umddi/D3D12DDIARG_CREATE_VIDEO_PROCESSOR_0032, display.d3d12ddiarg-create-video-processor-0032
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
-	D3D12DDIARG_CREATE_VIDEO_PROCESSOR_0032
product:
- Windows
targetos: Windows
tech.root: display
req.typenames: D3D12DDIARG_CREATE_VIDEO_PROCESSOR_0032
---

# D3D12DDIARG_CREATE_VIDEO_PROCESSOR_0032 structure


## -description


Creation arguments for creating the Video Processor.


## -struct-fields




### -field NodeMask

Represents the set of nodes. For single GPU operation, set this to zero. If there are multiple GPU nodes, set a bit to identify the node (the device's physical adapter) to which the command queue applies. Each bit in the mask corresponds to a single node. Only 1 bit may be set.


### -field OutputStream

Description of immutable output stream properties. See [D3D12DDI_VIDEO_PROCESS_OUTPUT_STREAM_DESC_0032](ns-d3d12umddi-d3d12ddi_video_process_output_stream_desc_0032.md).


### -field pInputStreams

An array of immutable input stream properties. See [D3D12DDI_VIDEO_PROCESSOR_INPUT_STREAM_DESC_0032](ns-d3d12umddi-d3d12ddi_video_processor_input_stream_desc_0032.md). The array size is defined by NumInputStreams.


### -field NumInputStreams

The count of input streams.

