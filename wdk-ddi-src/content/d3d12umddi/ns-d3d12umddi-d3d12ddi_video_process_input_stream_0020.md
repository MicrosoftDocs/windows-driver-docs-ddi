---
UID: NS:d3d12umddi.D3D12DDI_VIDEO_PROCESS_INPUT_STREAM_0020
title: D3D12DDI_VIDEO_PROCESS_INPUT_STREAM_0020 (d3d12umddi.h)
description: Contains stream information for the video processor blend functionality.
old-location: display\d3d12ddi_video_process_input_stream.htm
ms.assetid: DB0AF7A5-8E90-45B8-AF9C-58BFF7CE066E
ms.date: 05/10/2018
keywords: ["D3D12DDI_VIDEO_PROCESS_INPUT_STREAM_0020 structure"]
ms.keywords: D3D12DDI_VIDEO_PROCESS_INPUT_STREAM_0020, D3D12DDI_VIDEO_PROCESS_INPUT_STREAM_0020 structure [Display Devices], d3d12umddi/D3D12DDI_VIDEO_PROCESS_INPUT_STREAM_0020, display.d3d12ddi_video_process_input_stream
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
req.typenames: D3D12DDI_VIDEO_PROCESS_INPUT_STREAM_0020
f1_keywords:
 - D3D12DDI_VIDEO_PROCESS_INPUT_STREAM_0020
 - d3d12umddi/D3D12DDI_VIDEO_PROCESS_INPUT_STREAM_0020
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - D3d12umddi.h
api_name:
 - D3D12DDI_VIDEO_PROCESS_INPUT_STREAM_0020
---

# D3D12DDI_VIDEO_PROCESS_INPUT_STREAM_0020 structure


## -description

Contains stream information for the video processor blend functionality.

## -struct-fields

### -field hDrvInputTexture

The current input field or frame.

### -field Subresource

The subresource index to use of the <i>hDrvInputTexture</i> argument.

### -field ReferenceInfo

The set of references to be able to perform processing.

