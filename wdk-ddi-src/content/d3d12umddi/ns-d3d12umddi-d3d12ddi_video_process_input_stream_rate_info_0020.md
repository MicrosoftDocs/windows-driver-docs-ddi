---
UID: NS:d3d12umddi.D3D12DDI_VIDEO_PROCESS_INPUT_STREAM_RATE_INFO_0020
title: D3D12DDI_VIDEO_PROCESS_INPUT_STREAM_RATE_INFO_0020
author: windows-driver-content
description: Information for the input stream rate to use for video processing in a pattern, such as deinterlacing or frame-rate conversion.
old-location: display\d3d12ddi_video_process_input_stream_rate_info.htm
ms.assetid: 3F92B206-BA05-4ECC-854B-8D1EA9D7FD19
ms.author: windowsdriverdev
ms.date: 5/10/2018
ms.keywords: D3D12DDI_VIDEO_PROCESS_INPUT_STREAM_RATE_INFO_0020, D3D12DDI_VIDEO_PROCESS_INPUT_STREAM_RATE_INFO_0020 structure [Display Devices], d3d12umddi/D3D12DDI_VIDEO_PROCESS_INPUT_STREAM_RATE_INFO_0020, display.d3d12ddi_video_process_input_stream_rate_info
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
-	HeaderDef
api_location:
-	D3d12umddi.h
api_name:
-	D3D12DDI_VIDEO_PROCESS_INPUT_STREAM_RATE_INFO_0020
product:
- Windows
targetos: Windows
tech.root: display
req.typenames: D3D12DDI_VIDEO_PROCESS_INPUT_STREAM_RATE_INFO_0020
---

# D3D12DDI_VIDEO_PROCESS_INPUT_STREAM_RATE_INFO_0020 structure


## -description


Information for the input stream rate to use for video processing in a pattern, such as deinterlacing or frame-rate conversion.


## -struct-fields




### -field FrameRate

The frame rate of the input video stream, as a <a href="https://msdn.microsoft.com/0a878d11-dc90-4cad-bde5-54a135e53a86">DXGI_RATIONAL</a> structure.


### -field OutputIndex

The zero-based index of the output frame.


### -field InputFrameOrField

The zero-based index of the input frame or field.


## -see-also




<a href="https://msdn.microsoft.com/0a878d11-dc90-4cad-bde5-54a135e53a86">DXGI_RATIONAL</a>
 

 

