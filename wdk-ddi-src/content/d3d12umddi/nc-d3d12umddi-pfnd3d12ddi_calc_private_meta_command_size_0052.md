---
UID: NC:d3d12umddi.PFND3D12DDI_CALC_PRIVATE_META_COMMAND_SIZE_0052
title: PFND3D12DDI_CALC_PRIVATE_META_COMMAND_SIZE_0052 (d3d12umddi.h)
description: Learn more about the PFND3D12DDI_CALC_PRIVATE_META_COMMAND_SIZE_0052 callback function.
ms.date: 12/15/2023
keywords: ["PFND3D12DDI_CALC_PRIVATE_META_COMMAND_SIZE_0052 callback function"]
req.header: d3d12umddi.h
req.include-header: 
req.target-type: 
req.target-min-winverclnt: Windows 10, version 1809
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.lib: 
req.dll: 
req.irql: 
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
targetos: Windows
tech.root: display
ms.custom: RS5
f1_keywords:
 - PFND3D12DDI_CALC_PRIVATE_META_COMMAND_SIZE_0052
 - d3d12umddi/PFND3D12DDI_CALC_PRIVATE_META_COMMAND_SIZE_0052
topic_type:
 - apiref
api_type:
 - UserDefined
api_location:
 - d3d12umddi.h
api_name:
 - PFND3D12DDI_CALC_PRIVATE_META_COMMAND_SIZE_0052
dev_langs:
 - c++
---

# PFND3D12DDI_CALC_PRIVATE_META_COMMAND_SIZE_0052 callback function

## -description

**PFND3D12DDI_CALC_PRIVATE_META_COMMAND_SIZE_0052** calculates the private meta-command size.

## -parameters

### -param unnamedParam1

A handle to the display device (graphics context).

### -param CommandId

The command id.

### -param NodeMask

The node mask of the command list.

### -param pCreationParameters

Pointer to the creation parameters.

### -param CreationParametersDataSizeInBytes

The size in bytes of the creation parameters that **pCreationParameters** points to.

## -returns

Returns SIZE_T that describes the meta-command size, in bytes.
