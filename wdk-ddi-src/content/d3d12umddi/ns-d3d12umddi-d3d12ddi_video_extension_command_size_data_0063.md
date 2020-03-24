---
UID: NS:d3d12umddi.D3D12DDI_VIDEO_EXTENSION_COMMAND_SIZE_DATA_0063
title: D3D12DDI_VIDEO_EXTENSION_COMMAND_SIZE_DATA_0063
author: windows-driver-content
description: Queries the residency size information for a video extension command.
tech.root: display
ms.assetid: caf59d76-9a0e-4ac9-9b2a-f8ff32cab4da
ms.author: windowsdriverdev
ms.date: 04/04/2019
keywords: ["D3D12DDI_VIDEO_EXTENSION_COMMAND_SIZE_DATA_0063 structure"]
f1_keywords:
 - "d3d12umddi/D3D12DDI_VIDEO_EXTENSION_COMMAND_SIZE_DATA_0063"
ms.keywords: D3D12DDI_VIDEO_EXTENSION_COMMAND_SIZE_DATA_0063, D3D12DDI_VIDEO_EXTENSION_COMMAND_SIZE_DATA_0063, 
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
req.typenames: D3D12DDI_VIDEO_EXTENSION_COMMAND_SIZE_DATA_0063
topic_type: 
 - apiref
api_type: 
 - HeaderDef
api_location: 
 - d3d12umddi.h
api_name: 
 - D3D12DDI_VIDEO_EXTENSION_COMMAND_SIZE_DATA_0063
product:
- Windows
targetos: Windows
dev_langs:
 - c++
ms.custom: UMD DDI Min Version D3D12DDI_SUPPORTED_0043, 19H1
---

# D3D12DDI_VIDEO_EXTENSION_COMMAND_SIZE_DATA_0063 structure

## -description

Queries the residency size information for a video extension command.

## -struct-fields

### -field NodeIndex

[in] For single GPU operation, set this to zero. If there are multiple GPU nodes, set a bit to identify the node (the device's physical adapter) to which the command queue applies. Each bit in the mask corresponds to a single node. Only 1 bit may be set.

### -field CommandId

[in] The unique identifier for the video extension command.

### -field pCreationParameters

[in] Pointer to the initialization parameters structure. Parameters for this structure must match the parameter enumeration for [D3D12DDI_VIDEO_EXTENSION_COMMAND_PARAMETER_STAGE_0063_INITIALIZATION](ne-d3d12umddi-d3d12ddi_video_extension_command_parameter_stage_0063.md).

### -field CreationParametersSizeInBytes

[in] The size of the initialization parameters structure in bytes.

### -field MemoryPoolL0Size

[out] Indicates the command size in L0. L0 is the “closest” memory to the GPU. For discrete adapters, this is discrete graphics memory. For integrated adapters, this is typically the system memory size.

### -field MemoryPoolL1Size
 
[out] Indicates the command size in L1. L1 is the “next closest” memory for GPU. For discrete adapters, this is system memory. Integrated adapters do not typically have L1 and report zero size here.

## -remarks

Drivers must support the existing pfnMakeResident and pfnEvict with the D3D12DDI_HVIDEOEXTENSIONCOMMAND.

## -see-also
