---
UID: NC:d3d12umddi.PFND3D12DDI_DESTROYVIDEODECODER_0021
title: PFND3D12DDI_DESTROYVIDEODECODER_0021 (d3d12umddi.h)
description: Destroys the video decoder.
old-location: display\pfnd3d12ddi_destroyvideodecoder_.htm
ms.assetid: 97028FEB-A3C2-4C2F-B64E-07024BC3C382
ms.date: 04/16/2018
keywords: ["PFND3D12DDI_DESTROYVIDEODECODER_0021 callback function"]
ms.keywords: PFND3D12DDI_DESTROYVIDEODECODER_0021, PFND3D12DDI_DESTROYVIDEODECODER_0021 callback, PFND3D12DDI_DESTROYVIDEODECODER_0021 callback function [Display Devices], d3d12umddi/PFND3D12DDI_DESTROYVIDEODECODER_0021, display.pfnd3d12ddi_destroyvideodecoder_
f1_keywords:
 - "d3d12umddi/PFND3D12DDI_DESTROYVIDEODECODER_0021"
 - "PFND3D12DDI_DESTROYVIDEODECODER_0021"
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
- APIRef
- kbSyntax
api_type:
- UserDefined
api_location:
- D3d12umddi.h
api_name:
- PFND3D12DDI_DESTROYVIDEODECODER_0021
targetos: Windows
tech.root: display
req.typenames:
---

# PFND3D12DDI_DESTROYVIDEODECODER_0021 callback function


## -description


Destroys the video decoder.


## -parameters




### -param hDrvDevice

A handle to the display device (graphics context).

### -param hDrvVideoDecoder

Holds the HVideoDecoder


## -remarks

The decoder may be used to record commands with multiple command lists, but commands cannot be recorded simultaneously.  The application is responsible for synchronizing access to the decoder while recording commands.

Commands recorded against the decoder must also be executed in the order they were recorded. [Pfnd3d12ddiVideoDecodeFrame](nc-d3d12umddi-pfnd3d12ddi_video_decode_frame_0032.md) operations may modify the contents of the decoder’s internal resources when they are executed on the GPU and subsequent Pfnd3d12ddiVideoDecodeFrame operations may depend upon those modifications.

On a single queue, the application is responsible for calling execute command lists in the order that Pfnd3d12ddiVideoDecodeFrame commands were recorded with the decoder object.  When the application does so, the driver is then responsible for synchronizing Pfnd3d12ddiVideoDecodeFrame operations access to decoder resources.

When the application uses multiple queues with a single decoder object, the application is responsible for synchronizing and ordering the commands using fences.
