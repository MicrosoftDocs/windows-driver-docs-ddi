---
UID: NS:d3d12umddi.D3D12DDI_VIDEO_EXTENSION_COMMAND_PARAMETER_INFO_0063
title: D3D12DDI_VIDEO_EXTENSION_COMMAND_PARAMETER_INFO_0063
description: Contains info about a video extension command parameter info.
tech.root: display
ms.assetid: 74568b4c-5693-475b-9e72-69a499c1faf7
ms.date: 04/04/2019
keywords: ["D3D12DDI_VIDEO_EXTENSION_COMMAND_PARAMETER_INFO_0063 structure"]
ms.keywords: D3D12DDI_VIDEO_EXTENSION_COMMAND_PARAMETER_INFO_0063, D3D12DDI_VIDEO_EXTENSION_COMMAND_PARAMETER_INFO_0063,
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
req.typenames: D3D12DDI_VIDEO_EXTENSION_COMMAND_PARAMETER_INFO_0063
targetos: Windows
ms.custom: UMD DDI Min Version D3D12DDI_SUPPORTED_0043, 19H1
f1_keywords:
 - D3D12DDI_VIDEO_EXTENSION_COMMAND_PARAMETER_INFO_0063
 - d3d12umddi/D3D12DDI_VIDEO_EXTENSION_COMMAND_PARAMETER_INFO_0063
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - d3d12umddi.h
api_name:
 - D3D12DDI_VIDEO_EXTENSION_COMMAND_PARAMETER_INFO_0063
dev_langs:
 - c++
---

# D3D12DDI_VIDEO_EXTENSION_COMMAND_PARAMETER_INFO_0063 structure


## -description

Contains info about a video extension command parameter info.

## -struct-fields

### -field Name

Pointer to a wide string name of the parameter. The driver allocates and keeps for the lifetime of the device.

### -field Type

The parameter type. See [D3D12DDI_VIDEO_EXTENSION_COMMAND_PARAMETER_TYPE](ne-d3d12umddi-d3d12ddi_video_extension_command_parameter_type_0063.md).

### -field Flags

Parameter flags. See [D3D12DDI_VIDEO_EXTENSION_COMMAND_PARAMETER_FLAGS](ne-d3d12umddi-d3d12ddi_video_extension_command_parameter_flags_0063.md).

## -remarks

## -see-also

