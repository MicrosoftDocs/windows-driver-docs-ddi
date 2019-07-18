---
UID: NS:d3d12umddi.D3D12DDIARG_CREATE_VIDEO_PROCESSOR_0021
title: D3D12DDIARG_CREATE_VIDEO_PROCESSOR_0021 (d3d12umddi.h)
description: Specifies arguments used to create a video processor.
old-location: display\d3d12ddiarg_create_video_processor.htm
ms.assetid: 2FA77D7D-E1CC-44BA-8725-7132682A1BD6
ms.date: 05/10/2018
ms.keywords: D3D12DDIARG_CREATE_VIDEO_PROCESSOR_0021, D3D12DDIARG_CREATE_VIDEO_PROCESSOR_0021 structure [Display Devices], d3d12umddi/D3D12DDIARG_CREATE_VIDEO_PROCESSOR_0021, display.d3d12ddiarg_create_video_processor
ms.topic: struct
f1_keywords:
 - "d3d12umddi/D3D12DDIARG_CREATE_VIDEO_PROCESSOR_0021"
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
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- D3d12umddi.h
api_name:
- D3D12DDIARG_CREATE_VIDEO_PROCESSOR_0021
product:
- Windows
targetos: Windows
tech.root: display
req.typenames: D3D12DDIARG_CREATE_VIDEO_PROCESSOR_0021
---

# D3D12DDIARG_CREATE_VIDEO_PROCESSOR_0021 structure


## -description


Specifies arguments used to create a video processor.


## -struct-fields




### -field NodeMask

A node mask. For single GPU operation, set this value to zero (0). If there are multiple GPU nodes, set a bit to identify the physical adapter of the device to which the command queue applies. Each bit in the mask corresponds to a single node. Only one  bit may be set.


### -field Usage

Specifies a hint for the intended usage for the video processor. For more information, see the <a href="https://msdn.microsoft.com/663790EE-A9E3-4EBC-93C7-20DE0D759A26">D3D12DDI_VIDEO_USAGE</a> enumeration.


## -remarks



A video processor holds state for a video processing session. State includes required intermediate memory, cached processing data, or other temporary working space.  A separate video processor must be created for each content stream by the application.




## -see-also




<a href="https://msdn.microsoft.com/663790EE-A9E3-4EBC-93C7-20DE0D759A26">D3D12DDI_VIDEO_USAGE</a>
 

 

