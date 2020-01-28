---
UID: NS:d3d12umddi.D3D12DDI_VIDEO_EXTENSION_COMMANDS_DATA_0063
title: D3D12DDI_VIDEO_EXTENSION_COMMANDS_DATA_0063
author: windows-driver-content
description: Retrieves the array of video extension command info for a parameter stage.
tech.root: display
ms.assetid: 47a5a544-0d0e-418b-9378-ffb4e9dac7f1
ms.author: windowsdriverdev
ms.date: 04/04/2019
f1_keywords:
 - "d3d12umddi/D3D12DDI_VIDEO_EXTENSION_COMMANDS_DATA_0063"
ms.keywords: D3D12DDI_VIDEO_EXTENSION_COMMANDS_DATA_0063, D3D12DDI_VIDEO_EXTENSION_COMMANDS_DATA_0063, 
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
req.typenames: D3D12DDI_VIDEO_EXTENSION_COMMANDS_DATA_0063
topic_type: 
 - apiref
api_type: 
 - HeaderDef
api_location: 
 - d3d12umddi.h
api_name: 
 - D3D12DDI_VIDEO_EXTENSION_COMMANDS_DATA_0063
product:
- Windows
targetos: Windows
dev_langs:
 - c++
ms.custom: UMD DDI Min Version D3D12DDI_SUPPORTED_0043, 19H1
---

# D3D12DDI_VIDEO_EXTENSION_COMMANDS_DATA_0063 structure

## -description

Retrieves the array of video extension command info for a parameter stage.

## -struct-fields

### -field NodeIndex

[in] For single GPU operation, set this to zero. If there are multiple GPU nodes, set a bit to identify the node (the device's physical adapter) to which the command queue applies. Each bit in the mask corresponds to a single node. Only 1 bit may be set.

### -field CommandCount

[in] The number of video extension commands supported. This count must match the **CommandCount** returned by [D3D12DDI_VIDEO_EXTENSION_COMMAND_COUNT_DATA_0063](ns-d3d12umddi-d3d12ddi_video_extension_command_count_data_0063.md).

### -field pCommandInfos
 
[out] An array allocated by the runtime for the driver to fill with command info. **CommandCount** indicates the number of array elements.

## -remarks

## -see-also
