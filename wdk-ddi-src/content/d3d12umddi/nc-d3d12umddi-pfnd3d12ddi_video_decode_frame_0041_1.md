---
UID: NC:d3d12umddi.PFND3D12DDI_VIDEO_DECODE_FRAME_0041_1
title: PFND3D12DDI_VIDEO_DECODE_FRAME_0041_1
author: windows-driver-content
description:
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
topictype:
-	apiref
apitype:
-	UserDefined
apilocation:
-	d3d12umddi.h
apiname:
-	PFND3D12DDI_VIDEO_DECODE_FRAME_0041_1
product: Windows
targetos: Windows
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

The video decoder.

### -param *pOutputStreamParameters

The output arguments for the video decode.

### -param *pInputStreamParameters:

The input arguments for the video decode.

## -returns

This callback function does not return a value.




## -see-also