---
UID: NS:d3d12umddi.D3D12DDI_VIDEO_PROCESS_REFERENCES_INFO_0020
title: D3D12DDI_VIDEO_PROCESS_REFERENCES_INFO_0020 (d3d12umddi.h)
description: Contains the reference frames needed to perform video processing.
old-location: display\d3d12ddi_video_process_references_info.htm
ms.date: 04/16/2018
keywords: ["D3D12DDI_VIDEO_PROCESS_REFERENCES_INFO_0020 structure"]
ms.keywords: D3D12DDI_VIDEO_PROCESS_REFERENCES_INFO_0020, D3D12DDI_VIDEO_PROCESS_REFERENCES_INFO_0020 structure [Display Devices], d3d12umddi/D3D12DDI_VIDEO_PROCESS_REFERENCES_INFO_0020, display.d3d12ddi_video_process_references_info
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
targetos: Windows
tech.root: display
req.typenames: D3D12DDI_VIDEO_PROCESS_REFERENCES_INFO_0020
f1_keywords:
 - D3D12DDI_VIDEO_PROCESS_REFERENCES_INFO_0020
 - d3d12umddi/D3D12DDI_VIDEO_PROCESS_REFERENCES_INFO_0020
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - D3d12umddi.h
api_name:
 - D3D12DDI_VIDEO_PROCESS_REFERENCES_INFO_0020
---

# D3D12DDI_VIDEO_PROCESS_REFERENCES_INFO_0020 structure


## -description

Contains the reference frames needed to perform video processing.

## -struct-fields

### -field NumPastFrames

The number of past reference frames.

### -field hDrvPastFrames

A pointer to an array of surfaces. The number of elements in the array is the value of the <i>NumPastFrames</i> parameter.

### -field pPastSubresources

An array of subresource indexes for the list of past frames textures.  A value of null indicates subresource of zero (0) for each resource.

### -field NumFutureFrames

The number of future reference frames.

### -field hDrvFutureFrames

A pointer to an array of surfaces. The number of elements in the array is the value of  <i>NumFutureFrames</i> parameter.

### -field pFutureSubresources

An array of subresource indices for the list of future frames textures. A value of null indicates subresource 0 for each resource.

