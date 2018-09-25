---
UID: NC:d3d12umddi.PFND3D12DDI_VIDEO_DECODE_FRAME_0041_1
title: PFND3D12DDI_VIDEO_DECODE_FRAME_0041_1
author: windows-driver-content
description: Implemented by the client driver to decode a video frame.
ms.assetid: 9cb62916-22cb-42c6-925d-16cc320ddb5a
ms.author: windowsdriverdev
ms.date:
ms.topic: callback
ms.prod: windows-hardware
ms.technology: windows-devices
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
-	apiref
api_type:
-	UserDefined
api_location:
-	d3d12umddi.h
api_name:
-	PFND3D12DDI_VIDEO_DECODE_FRAME_0041_1
product: 
- Windows
targetos: Windows
tech.root: display
---

# PFND3D12DDI_VIDEO_DECODE_FRAME_0041_1 callback function

## -description

Implemented by the client driver to decode a video frame.

## -prototype

```
//Declaration

PFND3D12DDI_VIDEO_DECODE_FRAME_0041_1 Pfnd3d12ddiVideoDecodeFrame00411;

// Definition

VOID Pfnd3d12ddiVideoDecodeFrame00411
(
	D3D12DDI_HCOMMANDLIST hDrvCommandList
	D3D12DDI_HVIDEODECODER_0020 hDrvDecoder
	 const D3D12DDI_VIDEO_DECODE_OUTPUT_STREAM_ARGUMENTS_0041_1 *pOutputStreamParameters
	 const D3D12DDI_VIDEO_DECODE_INPUT_STREAM_ARGUMENTS_0032 *pInputStreamParameters
)
{...}

PFND3D12DDI_VIDEO_DECODE_FRAME_0041_1


```

## -parameters

### -param hDrvCommandList

A handle to the driver's data for the command list. The driver uses this region of memory to store internal data structures that are related to its command list.

### -param hDrvDecoder

The video decoder that contains internal state for this decode session.  Examples include motion vectors, internal temporary allocations, etc.  See [Creating a Video Decoder](https://docs.microsoft.com/windows-hardware/drivers/display/creating-a-video-decode-device).

### -param *pOutputStreamParameters

Specifies the output surface and output parameters. See [D3D12DDI_VIDEO_DECODE_OUTPUT_STREAM_ARGUMENTS](ns-d3d12umddi-d3d12ddi_video_decode_output_stream_arguments_0021.md).

### -param *pInputStreamParameters:

Specifies the input bit stream, parameters, reference frames, and other input parameters for the decode operation.  See [D3D12DDI_VIDEO_DECODE_INPUT_STREAM_ARGUMENTS](ns-d3d12umddi-d3d12ddi_video_decode_input_stream_arguments_0032.md).

## -returns

This callback function does not return a value.




## -see-also