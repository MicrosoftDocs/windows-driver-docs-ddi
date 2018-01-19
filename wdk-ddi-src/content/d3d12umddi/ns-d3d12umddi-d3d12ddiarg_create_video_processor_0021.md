---
UID: NS:d3d12umddi.D3D12DDIARG_CREATE_VIDEO_PROCESSOR_0021
title: D3D12DDIARG_CREATE_VIDEO_PROCESSOR_0021
author: windows-driver-content
description: Specifies arguments used to create a video processor.
old-location: display\d3d12ddiarg_create_video_processor.htm
old-project: display
ms.assetid: 2FA77D7D-E1CC-44BA-8725-7132682A1BD6
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: D3D12DDIARG_CREATE_VIDEO_PROCESSOR_0021, D3D12DDIARG_CREATE_VIDEO_PROCESSOR_0021
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
req.alt-api: D3D12DDIARG_CREATE_VIDEO_PROCESSOR_0021
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
req.typenames: D3D12DDIARG_CREATE_VIDEO_PROCESSOR_0021
---

# D3D12DDIARG_CREATE_VIDEO_PROCESSOR_0021 structure



## -description
Specifies arguments used to create a video processor.



## -syntax

````
typedef struct D3D12DDIARG_CREATE_VIDEO_PROCESSOR_0021 {
  UINT                 NodeMask;
  D3D12DDI_VIDEO_USAGE Usage;
} D3D12DDIARG_CREATE_VIDEO_PROCESSOR_0021;
````


## -struct-fields

### -field NodeMask

A node mask. For single GPU operation, set this value to zero (0). If there are multiple GPU nodes, set a bit to identify the physical adapter of the device to which the command queue applies. Each bit in the mask corresponds to a single node. Only one  bit may be set.


### -field Usage

Specifies a hint for the intended usage for the video processor. For more information, see the <a href="..\d3d12umddi\ne-d3d12umddi-d3d12ddi_video_usage.md">D3D12DDI_VIDEO_USAGE</a> enumeration.


## -remarks
A video processor holds state for a video processing session. State includes required intermediate memory, cached processing data, or other temporary working space.  A separate video processor must be created for each content stream by the application.  


## -see-also
<dl>
<dt>
<a href="..\d3d12umddi\ne-d3d12umddi-d3d12ddi_video_usage.md">D3D12DDI_VIDEO_USAGE</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20D3D12DDIARG_CREATE_VIDEO_PROCESSOR_0021 structure%20 RELEASE:%20(12/29/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

