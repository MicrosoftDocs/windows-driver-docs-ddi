---
UID: NE:d3d12umddi.D3D12DDI_VIDEO_EXTENSION_COMMAND_PARAMETER_STAGE_0063
title: D3D12DDI_VIDEO_EXTENSION_COMMAND_PARAMETER_STAGE_0063
description: Video Extensions support different parameterization at creation, initialization, and execution.
tech.root: display
ms.date: 05/24/2022
keywords: ["D3D12DDI_VIDEO_EXTENSION_COMMAND_PARAMETER_STAGE_0063 enumeration"]
ms.keywords: D3D12DDI_VIDEO_EXTENSION_COMMAND_PARAMETER_STAGE_0063, D3D12DDI_VIDEO_EXTENSION_COMMAND_PARAMETER_STAGE_0063,
req.header: d3d12umddi.h
req.include-header: 
req.target-type: 
req.target-min-winverclnt: Windows 10, version 1903
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: 
req.max-support: 
req.typenames: D3D12DDI_VIDEO_EXTENSION_COMMAND_PARAMETER_STAGE_0063
targetos: Windows
ms.custom: UMD DDI Min Version D3D12DDI_SUPPORTED_0043, 19H1
f1_keywords:
 - D3D12DDI_VIDEO_EXTENSION_COMMAND_PARAMETER_STAGE_0063
 - d3d12umddi/D3D12DDI_VIDEO_EXTENSION_COMMAND_PARAMETER_STAGE_0063
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - d3d12umddi.h
api_name:
 - D3D12DDI_VIDEO_EXTENSION_COMMAND_PARAMETER_STAGE_0063
dev_langs:
 - c++
---

# D3D12DDI_VIDEO_EXTENSION_COMMAND_PARAMETER_STAGE_0063 enumeration

## -description

**D3D12DDI_VIDEO_EXTENSION_COMMAND_PARAMETER_STAGE_0063** specifies the parameter stages for video extension commands.

## -enum-fields

### -field D3D12DDI_VIDEO_EXTENSION_COMMAND_PARAMETER_STAGE_0063_CREATION:0

The parameter stage is in video extension command creation.

### -field D3D12DDI_VIDEO_EXTENSION_COMMAND_PARAMETER_STAGE_0063_INITIALIZATION:1

The parameter stage is in video extension command initialization.

### -field D3D12DDI_VIDEO_EXTENSION_COMMAND_PARAMETER_STAGE_0063_EXECUTION:2

The parameter stage is in video extension command execution.

### -field D3D12DDI_VIDEO_EXTENSION_COMMAND_PARAMETER_STAGE_0063_CAPS_INPUT:3

The parameter stage is input parameters passed to capabilities queries.

### -field D3D12DDI_VIDEO_EXTENSION_COMMAND_PARAMETER_STAGE_0063_CAPS_OUTPUT:4

The parameter stage is output parameters passed to capabilities queries.

### -field D3D12DDI_VIDEO_EXTENSION_COMMAND_PARAMETER_STAGE_0076_DEVICE_EXECUTE_INPUT:5

The parameter stage is device execution input.

### -field D3D12DDI_VIDEO_EXTENSION_COMMAND_PARAMETER_STAGE_0076_DEVICE_EXECUTE_OUTPUT:6

The parameter stage is device execution input.

## -remarks

Video Extensions support different parameterization at creation, initialization, and execution. Values from this enumeration are used when querying for video extension parameter information.
