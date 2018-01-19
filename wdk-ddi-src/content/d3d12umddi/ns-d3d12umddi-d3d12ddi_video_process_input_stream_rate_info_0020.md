---
UID: NS:d3d12umddi.D3D12DDI_VIDEO_PROCESS_INPUT_STREAM_RATE_INFO_0020
title: D3D12DDI_VIDEO_PROCESS_INPUT_STREAM_RATE_INFO_0020
author: windows-driver-content
description: Information for the input stream rate to use for video processing in a pattern, such as deinterlacing or frame-rate conversion.
old-location: display\d3d12ddi_video_process_input_stream_rate_info.htm
old-project: display
ms.assetid: 3F92B206-BA05-4ECC-854B-8D1EA9D7FD19
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: D3D12DDI_VIDEO_PROCESS_INPUT_STREAM_RATE_INFO_0020, D3D12DDI_VIDEO_PROCESS_INPUT_STREAM_RATE_INFO_0020
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
req.alt-api: D3D12DDI_VIDEO_PROCESS_INPUT_STREAM_RATE_INFO_0020
req.alt-loc: D3d12umddi.h
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
req.typenames: D3D12DDI_VIDEO_PROCESS_INPUT_STREAM_RATE_INFO_0020
---

# D3D12DDI_VIDEO_PROCESS_INPUT_STREAM_RATE_INFO_0020 structure



## -description
Information for the input stream rate to use for video processing in a pattern, such as deinterlacing or frame-rate conversion. 



## -syntax

````
typedef struct D3D12DDI_VIDEO_PROCESS_INPUT_STREAM_RATE_INFO_0020 {
  DXGI_RATIONAL FrameRate;
  UINT          OutputIndex;
  UINT          InputFrameOrField;
} D3D12DDI_VIDEO_PROCESS_INPUT_STREAM_RATE_INFO_0020;
````


## -struct-fields

### -field FrameRate

The frame rate of the input video stream, as a <a href="https://msdn.microsoft.com/0a878d11-dc90-4cad-bde5-54a135e53a86">DXGI_RATIONAL</a> structure.


### -field OutputIndex

The zero-based index of the output frame. 


### -field InputFrameOrField

The zero-based index of the input frame or field.


## -remarks


## -see-also
<dl>
<dt>
<a href="https://msdn.microsoft.com/0a878d11-dc90-4cad-bde5-54a135e53a86">DXGI_RATIONAL</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20D3D12DDI_VIDEO_PROCESS_INPUT_STREAM_RATE_INFO_0020 structure%20 RELEASE:%20(12/29/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

