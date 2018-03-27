---
UID: NC:d3d12umddi.PFND3D12DDI_VIDEO_DECODE_FRAME_0021
title: PFND3D12DDI_VIDEO_DECODE_FRAME_0021
author: windows-driver-content
description: The pfnDecodeFrame callback function records a decode frame operation to the command list.
old-location: display\pfnd3d12ddi_video_decode_frame.htm
old-project: display
ms.assetid: 8EA34C58-9B2D-4B69-ABAB-D67F6BCD6229
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: PFND3D12DDI_VIDEO_DECODE_FRAME_0021, d3d12umddi/pfnDecodeFrame, display.pfnd3d12ddi_video_decode_frame, pfnDecodeFrame, pfnDecodeFrame callback function [Display Devices]
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
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
req.max-support: Windows 10, version 1709
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
-	UserDefined
api_location:
-	D3d12umddi.h
api_name:
-	pfnDecodeFrame
product: Windows
targetos: Windows
req.typenames: D3D11_1DDI_GETCAPTUREHANDLEDATA
---

# PFND3D12DDI_VIDEO_DECODE_FRAME_0021 callback


## -description


The <i>pfnDecodeFrame</i> callback function records a decode frame operation to the command list.


## -prototype


````
PFND3D12DDI_VIDEO_DECODE_FRAME_0021 pfnDecodeFrame;

VOID  APIENTRY* pfnDecodeFrame(
         D3D12DDI_HCOMMANDLIST                         hDrvCommandList,
         UINT64                                        SubmissionID,
         D3D12DDI_HVIDEODECODER                        hDrvDecoder,
   const D3D12DDI_VIDEO_DECODE_OUTPUT_STREAM_ARGUMENTS *pOutputStreamArguments,
   const D3D12DDI_VIDEO_DECODE_INPUT_STREAM_ARGUMENTS  *pInputStreamArguments
)
{ ... }
````


## -parameters




### -param hDrvCommandList

The command list used to record this process frames command.


### -param hDrvDecoder

The video decoder that contains internal state for this decode session.  Examples include motion vectors and internal temporary allocations.


### -param SubmissionID

The submission ID is a monotonically increasing integer value.  The value passed to this function must be larger than any passed decode frame submission for the decoder specified by the <i>hDrvVideoDecoder</i> parameter.  Callers should use fences to track submission completion and then provide completed submission IDs to drivers by using <a href="..\d3d12umddi\nc-d3d12umddi-pfnd3d12ddi_video_decoder_trim_allocations_0021.md">pfnDecoderTrimAllocations</a> to allow driver to manage resources associated with that decoder.


### -param *pOutputStreamParameters


### -param *pInputStreamParameters








#### - pInputStreamArguments

The input bitstream, parameters, reference frames, and other input parameters for the decode operation.  For more information, see the <a href="..\d3d12umddi\ns-d3d12umddi-d3d12ddi_video_decode_input_stream_arguments_0020.md">D3D12DDI_VIDEO_DECODE_INPUT_STREAM_ARGUMENTS</a> structure.


#### - pOutputStreamArguments

The output surface and output parameters.  For more information, see the <a href="..\d3d12umddi\ns-d3d12umddi-d3d12ddi_video_decode_output_stream_arguments_0021.md">D3D12DDI_VIDEO_DECODE_OUTPUT_STREAM_ARGUMENTS</a> structure.


## -returns



This callback function does not return a value.




## -see-also

<a href="..\d3d12umddi\nc-d3d12umddi-pfnd3d12ddi_video_decoder_trim_allocations_0021.md">pfnDecoderTrimAllocations</a>



<a href="..\d3d12umddi\ns-d3d12umddi-d3d12ddi_video_decode_input_stream_arguments_0020.md">D3D12DDI_VIDEO_DECODE_INPUT_STREAM_ARGUMENTS</a>



<a href="..\d3d12umddi\ns-d3d12umddi-d3d12ddi_video_decode_output_stream_arguments_0021.md">D3D12DDI_VIDEO_DECODE_OUTPUT_STREAM_ARGUMENTS</a>



 

 


