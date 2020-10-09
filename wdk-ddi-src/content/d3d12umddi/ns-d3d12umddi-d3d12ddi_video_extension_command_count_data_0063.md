---
UID: NS:d3d12umddi.D3D12DDI_VIDEO_EXTENSION_COMMAND_COUNT_DATA_0063
title: D3D12DDI_VIDEO_EXTENSION_COMMAND_COUNT_DATA_0063
description: Retrieves the number of supported video extension commands.
tech.root: display
ms.assetid: 19013676-88c2-4603-bf40-2205f647ac0a
ms.date: 04/04/2019
keywords: ["D3D12DDI_VIDEO_EXTENSION_COMMAND_COUNT_DATA_0063 structure"]
ms.keywords: D3D12DDI_VIDEO_EXTENSION_COMMAND_COUNT_DATA_0063, D3D12DDI_VIDEO_EXTENSION_COMMAND_COUNT_DATA_0063,
req.header: d3d12umddi.h
req.include-header: 
req.target-type: 
req.target-min-winverclnt: Windows 10, version 1903
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.lib: 
req.dll: 
req.ddi-compliance: 
req.unicode-ansi: 
req.max-support: 
req.typenames: D3D12DDI_VIDEO_EXTENSION_COMMAND_COUNT_DATA_0063
targetos: Windows
ms.custom: UMD DDI Min Version D3D12DDI_SUPPORTED_0043, 19H1
f1_keywords:
 - D3D12DDI_VIDEO_EXTENSION_COMMAND_COUNT_DATA_0063
 - d3d12umddi/D3D12DDI_VIDEO_EXTENSION_COMMAND_COUNT_DATA_0063
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - d3d12umddi.h
api_name:
 - D3D12DDI_VIDEO_EXTENSION_COMMAND_COUNT_DATA_0063
dev_langs:
 - c++
---

# D3D12DDI_VIDEO_EXTENSION_COMMAND_COUNT_DATA_0063 structure


## -description

Retrieves the number of supported video extension commands.

## -struct-fields

### -field NodeIndex

[in] For single GPU operation, set this to zero. If there are multiple GPU nodes, set a bit to identify the node (the device's physical adapter) to which the command queue applies. Each bit in the mask corresponds to a single node. Only 1 bit may be set.

### -field CommandCount

 
[out] The number of video extension commands supported.

## -remarks

## -see-also

