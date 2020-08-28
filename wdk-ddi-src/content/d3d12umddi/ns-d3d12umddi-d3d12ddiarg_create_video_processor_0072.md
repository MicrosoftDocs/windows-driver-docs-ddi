---
UID: NS:d3d12umddi.D3D12DDIARG_CREATE_VIDEO_PROCESSOR_0072
title: D3D12DDIARG_CREATE_VIDEO_PROCESSOR_0072
ms.date: 03/24/2020
ms.topic: language-reference
ms.assetid: 0d0d93df-2f90-4bc5-be25-3a734dbc494e
tech.root: display
targetos: Windows
description: Used to create a video processor.
req.construct-type: structure
req.ddi-compliance: 
req.dll: 
req.header: d3d12umddi.h
req.include-header: 
req.kmdf-ver: 
req.lib: 
req.max-support: 
req.redist: 
req.target-min-winverclnt: Windows 10, version 2004
req.target-min-winversvr: 
req.target-type: 
req.typenames: D3D12DDIARG_CREATE_VIDEO_PROCESSOR_0072
req.umdf-ver: 
req.unicode-ansi: 
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - d3d12umddi.h
api_name:
 - D3D12DDIARG_CREATE_VIDEO_PROCESSOR_0072
f1_keywords:
 - D3D12DDIARG_CREATE_VIDEO_PROCESSOR_0072
 - d3d12umddi/D3D12DDIARG_CREATE_VIDEO_PROCESSOR_0072
dev_langs:
 - c++
---

## -description

Used to create a video processor.

## -struct-fields

### -field NodeMask

Represents the set of nodes.

### -field OutputStream

A [**D3D12DDI_VIDEO_PROCESS_OUTPUT_STREAM_DESC_0032**](ns-d3d12umddi-d3d12ddi_video_process_output_stream_desc_0032.md) structure describing the output stream.

### -field pInputStreams

Pointer to a [**D3D12DDI_VIDEO_PROCESSOR_INPUT_STREAM_DESC_0043**](ns-d3d12umddi-d3d12ddi_video_process_input_stream_desc_0043.md) structure for the input stream.

### -field NumInputStreams

Number of input streams.

### -field hDrvProtectedResourceSession

Handle to the protected resource session acquired at object creation time.

## -remarks

## -see-also

[**PFND3D12DDI_CREATEVIDEOPROCESSOR_0072**](nc-d3d12umddi-pfnd3d12ddi_createvideoprocessor_0072.md)

