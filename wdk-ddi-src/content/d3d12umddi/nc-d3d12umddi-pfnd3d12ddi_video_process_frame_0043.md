---
UID: NC:d3d12umddi.PFND3D12DDI_VIDEO_PROCESS_FRAME_0043
title: PFND3D12DDI_VIDEO_PROCESS_FRAME_0043 (d3d12umddi.h)
description: Implemented by the client driver to process a video frame.
ms.assetid: cd60f939-e9f0-408b-8bb3-709bd7d14fdc
ms.date: 10/19/2018
ms.topic: callback
f1_keywords:
 - "d3d12umddi/PFND3D12DDI_VIDEO_PROCESS_FRAME_0043"
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
topic_type:
- apiref
api_type:
- UserDefined
api_location:
- d3d12umddi.h
api_name:
- PFND3D12DDI_VIDEO_PROCESS_FRAME_0043
product: 
- Windows
targetos: Windows
tech.root: display
---

# PFND3D12DDI_VIDEO_PROCESS_FRAME_0043 callback function

## -description

Implemented by the client driver to process a video frame.

## -prototype

```cpp
//Declaration

PFND3D12DDI_VIDEO_PROCESS_FRAME_0043 Pfnd3d12ddiVideoProcessFrame0043;

// Definition

VOID Pfnd3d12ddiVideoProcessFrame0043
(
	D3D12DDI_HCOMMANDLIST hDrvCommandList
	D3D12DDI_HVIDEOPROCESSOR_0020 hDrvVideoProcessor
	 const D3D12DDIARG_VIDEO_PROCESS_OUTPUT_STREAM_ARGUMENTS_0032 *pOutputParameters
	 const D3D12DDIARG_VIDEO_PROCESS_INPUT_STREAM_ARGUMENTS_0043 *pInputStreamParameters
	UINT NumInputStreams
)
{...}

PFND3D12DDI_VIDEO_PROCESS_FRAME_0043


```

## -parameters

### -param hDrvCommandList

A handle to the driver's data for the command list. The driver uses this region of memory to store internal data structures that are related to its command list.

### -param hDrvVideoProcessor

The video processor.

### -param *pOutputParameters

The output arguments for the video process.

### -param *pInputStreamParameters

The input arguments for the video process.

### -param NumInputStreams:

The number of input streams.

## -returns

This callback function does not return a value.


## -see-also
