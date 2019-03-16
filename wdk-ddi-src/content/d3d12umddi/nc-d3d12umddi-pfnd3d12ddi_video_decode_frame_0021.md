---
UID: NC:d3d12umddi.PFND3D12DDI_VIDEO_DECODE_FRAME_0021
title: PFND3D12DDI_VIDEO_DECODE_FRAME_0021 (d3d12umddi.h)
description: The pfnDecodeFrame callback function records a decode frame operation to the command list.
old-location: display\pfnd3d12ddi_video_decode_frame.htm
ms.assetid: 8EA34C58-9B2D-4B69-ABAB-D67F6BCD6229
ms.date: 05/10/2018
ms.keywords: PFND3D12DDI_VIDEO_DECODE_FRAME_0021, PFND3D12DDI_VIDEO_DECODE_FRAME_0021 callback, d3d12umddi/pfnDecodeFrame, display.pfnd3d12ddi_video_decode_frame, pfnDecodeFrame, pfnDecodeFrame callback function [Display Devices]
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
- APIRef
- kbSyntax
api_type:
- UserDefined
api_location:
- D3d12umddi.h
api_name:
- pfnDecodeFrame
product:
- Windows
targetos: Windows
tech.root: display
req.typenames: 
---

# PFND3D12DDI_VIDEO_DECODE_FRAME_0021 callback function


## -description


The <i>pfnDecodeFrame</i> callback function records a decode frame operation to the command list.


## -parameters




### -param hDrvCommandList

The command list used to record this process frames command.


### -param hDrvDecoder

The video decoder that contains internal state for this decode session.  Examples include motion vectors and internal temporary allocations.


### -param SubmissionID

The submission ID is a monotonically increasing integer value.  The value passed to this function must be larger than any passed decode frame submission for the decoder specified by the <i>hDrvVideoDecoder</i> parameter.  Callers should use fences to track submission completion and then provide completed submission IDs to drivers by using <a href="https://msdn.microsoft.com/2E90B365-8C5D-4586-AAA8-D49CC9BBCF70">pfnDecoderTrimAllocations</a> to allow driver to manage resources associated with that decoder.


### -param *pOutputStreamParameters

The output surface and output parameters.  For more information, see the <a href="https://msdn.microsoft.com/4179447D-481F-4EC3-922C-4DFE3F5D768F">D3D12DDI_VIDEO_DECODE_OUTPUT_STREAM_ARGUMENTS</a> structure. 

### -param *pInputStreamParameters

The input bitstream, parameters, reference frames, and other input parameters for the decode operation.  For more information, see the <a href="https://msdn.microsoft.com/B956626C-B5D7-4217-A90A-EC7E436DF6C0">D3D12DDI_VIDEO_DECODE_INPUT_STREAM_ARGUMENTS</a> structure.



## -returns



This callback function does not return a value.




## -see-also




<a href="https://msdn.microsoft.com/B956626C-B5D7-4217-A90A-EC7E436DF6C0">D3D12DDI_VIDEO_DECODE_INPUT_STREAM_ARGUMENTS</a>



<a href="https://msdn.microsoft.com/4179447D-481F-4EC3-922C-4DFE3F5D768F">D3D12DDI_VIDEO_DECODE_OUTPUT_STREAM_ARGUMENTS</a>



<a href="https://msdn.microsoft.com/2E90B365-8C5D-4586-AAA8-D49CC9BBCF70">pfnDecoderTrimAllocations</a>
 

 

