---
UID: NC:d3d12umddi.PFND3D12DDI_VIDEO_PROCESS_FRAME_0021
title: PFND3D12DDI_VIDEO_PROCESS_FRAME_0021
author: windows-driver-content
description: The pfnProcessFrame callback function performs a video processing operation on one or more input samples and writes the result to an output surface.
old-location: display\pfnd3d12ddi_video_process_frame.htm
old-project: display
ms.assetid: C4908916-D91F-4E89-A17B-87ABF3546C6A
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: PFND3D12DDI_VIDEO_PROCESS_FRAME_0021, d3d12umddi/pfnProcessFrame, display.pfnd3d12ddi_video_process_frame, pfnProcessFrame, pfnProcessFrame callback function [Display Devices]
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
-	pfnProcessFrame
product: Windows
targetos: Windows
req.typenames: D3D11_1DDI_GETCAPTUREHANDLEDATA
---

# PFND3D12DDI_VIDEO_PROCESS_FRAME_0021 callback


## -description


The <i>pfnProcessFrame</i> callback function performs a video processing operation on one or more input samples and writes the result to an output surface.


## -prototype


````
PFND3D12DDI_VIDEO_PROCESS_FRAME_0021 pfnProcessFrame;

VOID APIENTRY* pfnProcessFrame(
         D3D12DDI_HCOMMANDLIST                             hDrvCommandList,
         D3D12DDI_HVIDEOPROCESSOR                          hDrvVideoProcessor,
         UINT64                                            SubmissionID,
   const D3D12DDIARG_VIDEO_PROCESS_OUTPUT_STREAM_PARAMS    *pOutputParameters,
   const D3D12DDIARG_VIDEO_PROCESS_INPUT_STREAM_PARAMETERS *pInputStreamParameters,
         UINT                                              NumInputStreams
)
{ ... }
````


## -parameters




### -param hDrvCommandList

The command list used to record this process frames command.


### -param hDrvVideoProcessor

The video processor instance to use for this video process call.


### -param SubmissionID

The submission ID is a monotonically increasing integer value.  The value passed to this function must be larger than any passed video process submission for the <i>hDrvVideoProcessor</i> parameter.  Callers should use fences to track submission completion and then provide completed submission ID to drivers by using the <a href="..\d3d12umddi\nc-d3d12umddi-pfnd3d12ddi_video_processor_trim_allocations_0021.md">pfnProcessorTrimAllocations</a> function to allow driver to manage resources associated with that stream.


### -param *pOutputParameters

The output parameters.  For more information, see the <a href="..\d3d12umddi\ns-d3d12umddi-d3d12ddiarg_video_process_output_stream_arguments_0020.md">D3D12DDIARG_VIDEO_PROCESS_OUTPUT_STREAM_PARAMETERS</a> structure.


### -param *pInputStreamParameters

Specifies an array of input parameters.  For more information, see the <a href="..\d3d12umddi\ns-d3d12umddi-d3d12ddiarg_video_process_input_stream_arguments_0020.md">D3D12DDIARG_VIDEO_PROCESS_INPUT_STREAM_PARAMETERS</a> structure.


### -param NumInputStreams


## -returns



This callback function does not return a value.




## -see-also

<a href="..\d3d12umddi\ns-d3d12umddi-d3d12ddiarg_video_process_output_stream_arguments_0020.md">D3D12DDIARG_VIDEO_PROCESS_OUTPUT_STREAM_PARAMETERS</a>



<a href="..\d3d12umddi\ns-d3d12umddi-d3d12ddiarg_video_process_input_stream_arguments_0020.md">D3D12DDIARG_VIDEO_PROCESS_INPUT_STREAM_PARAMETERS</a>



<a href="..\d3d12umddi\nc-d3d12umddi-pfnd3d12ddi_video_processor_trim_allocations_0021.md">pfnProcessorTrimAllocations</a>



 

 


