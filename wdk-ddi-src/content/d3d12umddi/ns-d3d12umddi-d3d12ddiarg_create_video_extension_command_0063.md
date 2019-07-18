---
UID: NS:d3d12umddi.D3D12DDIARG_CREATE_VIDEO_EXTENSION_COMMAND_0063
title: D3D12DDIARG_CREATE_VIDEO_EXTENSION_COMMAND_0063
author: windows-driver-content
description: Used to create a video extension command.
tech.root: display
ms.assetid: 5b621cc0-5062-44ab-8d1e-ddd88e10b1eb
ms.author: windowsdriverdev
ms.date: 04/04/2019
ms.topic: struct
f1_keywords:
 - "d3d12umddi/D3D12DDIARG_CREATE_VIDEO_EXTENSION_COMMAND_0063"
ms.keywords: D3D12DDIARG_CREATE_VIDEO_EXTENSION_COMMAND_0063, D3D12DDIARG_CREATE_VIDEO_EXTENSION_COMMAND_0063, 
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
req.typenames: D3D12DDIARG_CREATE_VIDEO_EXTENSION_COMMAND_0063
topic_type: 
 - apiref
api_type: 
 - HeaderDef
api_location: 
 - d3d12umddi.h
api_name: 
 - D3D12DDIARG_CREATE_VIDEO_EXTENSION_COMMAND_0063
product:
- Windows
targetos: Windows
ms.custom: UMD DDI Min Version D3D12DDI_SUPPORTED_0043, 19H1
---

# D3D12DDIARG_CREATE_VIDEO_EXTENSION_COMMAND_0063 structure

## -description

Contains arguments used to create a video extension command.

## -struct-fields

### -field NodeMask

[in] For single GPU operation, set this to zero. If there are multiple GPU nodes, set a bit to identify the node (the device's physical adapter) to which the command queue applies. Each bit in the mask corresponds to a single node. Only 1 bit may be set.

### -field CommandId

[in] The unique identifier for the video extension command.

### -field pCreationParameters

[in] Pointer to the creation parameters structure. Parameters for this structure must match the parameter enumeration for [D3D12DDI_VIDEO_EXTENSION_COMMAND_PARAMETER_STAGE_0063_CREATION](ne-d3d12umddi-d3d12ddi_video_extension_command_parameter_stage_0063.md).

### -field CreationParametersDataSizeInBytes

The size of the creation parameters structure in bytes.

### -field hDrvProtectedResourceSession
 
Handle to the D3D12DDI_HPROTECTEDRESOURCESESSION_0030. Runtime has allocated space according to the result of PFND3D12DDI_CALC_PRIVATE_VIDEO_EXTENSION_COMMAND_SIZE for the driver to place its object.

## -remarks

## -see-also
