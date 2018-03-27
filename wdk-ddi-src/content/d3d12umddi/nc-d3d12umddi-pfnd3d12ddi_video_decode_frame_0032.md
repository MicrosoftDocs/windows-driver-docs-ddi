---
UID: NC:d3d12umddi.PFND3D12DDI_VIDEO_DECODE_FRAME_0032
title: PFND3D12DDI_VIDEO_DECODE_FRAME_0032
author: windows-driver-content
description: Used to decode a video frame.
old-location: display\pfnd3d12ddi_video_decode_frame_0032.htm
old-project: display
ms.assetid: 0E7DC432-64F9-4EDE-B0FC-5F65EB9E68AD
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: PFND3D12DDI_VIDEO_DECODE_FRAME_0030, PFND3D12DDI_VIDEO_DECODE_FRAME_0030 callback function [Display Devices], d3d12umddi/PFND3D12DDI_VIDEO_DECODE_FRAME_0030, display.pfnd3d12ddi_video_decode_frame_0032
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
-	UserDefined
api_location:
-	d3d12umddi.h
api_name:
-	PFND3D12DDI_VIDEO_DECODE_FRAME_0030
product: Windows
targetos: Windows
req.typenames: D3D11_1DDI_GETCAPTUREHANDLEDATA
---

# PFND3D12DDI_VIDEO_DECODE_FRAME_0032 callback


## -description


Used to decode a video frame.


## -parameters




### -param hDrvCommandList

The command list.


### -param hDrvDecoder

The video decoder.


### -param *pOutputStreamParameters

The output arguments for the video decode.


### -param *pInputStreamParameters

The input arguments for the video decode.


#### - SubmissionID

The submission ID.


## -returns



This callback function does not return a value.



