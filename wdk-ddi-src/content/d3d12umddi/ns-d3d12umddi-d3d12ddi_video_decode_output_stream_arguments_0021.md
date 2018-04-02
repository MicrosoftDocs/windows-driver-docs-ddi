---
UID: NS:d3d12umddi.D3D12DDI_VIDEO_DECODE_OUTPUT_STREAM_ARGUMENTS_0021
title: D3D12DDI_VIDEO_DECODE_OUTPUT_STREAM_ARGUMENTS_0021
author: windows-driver-content
description: Output stream arguments for video decode.
old-location: display\d3d12ddi_video_decode_output_stream_arguments.htm
old-project: display
ms.assetid: 4179447D-481F-4EC3-922C-4DFE3F5D768F
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: D3D12DDI_VIDEO_DECODE_OUTPUT_STREAM_ARGUMENTS_0021, D3D12DDI_VIDEO_DECODE_OUTPUT_STREAM_ARGUMENTS_0021 structure [Display Devices], d3d12umddi/D3D12DDI_VIDEO_DECODE_OUTPUT_STREAM_ARGUMENTS_0021, display.d3d12ddi_video_decode_output_stream_arguments
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: d3d12umddi.h
req.include-header: D3d12umddi.h
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
-	D3d12umddi.h
api_name:
-	D3D12DDI_VIDEO_DECODE_OUTPUT_STREAM_ARGUMENTS_0021
product:
- Windows
targetos: Windows
req.typenames: D3D12DDI_VIDEO_DECODE_OUTPUT_STREAM_ARGUMENTS_0021
---

# D3D12DDI_VIDEO_DECODE_OUTPUT_STREAM_ARGUMENTS_0021 structure


## -description


Output stream arguments for video decode.


## -struct-fields




### -field hDrvOutputTexture2D

The output texture.  If decode conversion is enabled, this output specifies the post conversion output.  If decode conversion is not enabled, this is the decode output.


### -field OutputSubresource

The output subresource to use for the <i>hDrvOutputTexture2D</i> parameter. If the output is an array, this allows specifying array indices.


### -field ConversionArguments

 




#### - ConversionParameters

Optional output conversion parameters.

