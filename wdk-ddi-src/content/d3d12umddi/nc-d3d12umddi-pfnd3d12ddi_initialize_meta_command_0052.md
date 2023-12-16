---
UID: NC:d3d12umddi.PFND3D12DDI_INITIALIZE_META_COMMAND_0052
title: PFND3D12DDI_INITIALIZE_META_COMMAND_0052 (d3d12umddi.h)
description: Learn more about the D3D12DDI_INITIALIZE_META_COMMAND_0052 callback function.
ms.date: 12/15/2023
keywords: ["PFND3D12DDI_INITIALIZE_META_COMMAND_0052 callback function"]
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
 - PFND3D12DDI_INITIALIZE_META_COMMAND_0052
 - d3d12umddi/PFND3D12DDI_INITIALIZE_META_COMMAND_0052
topic_type:
 - apiref
api_type:
 - UserDefined
api_location:
 - d3d12umddi.h
api_name:
 - PFND3D12DDI_INITIALIZE_META_COMMAND_0052
product:
 - Windows
dev_langs:
 - c++
---

# PFND3D12DDI_INITIALIZE_META_COMMAND_0052 callback function

## -description

**PFND3D12DDI_INITIALIZE_META_COMMAND_0052** initializes a meta-command.

## -parameters

### -param unnamedParam1

A handle to the driver's data for the command list. The driver uses this region of memory to store internal data structures that are related to its command list.

### -param unnamedParam2

A handle to a meta-command.

### -param unnamedParam3

A pointer to the execution parameters for the meta-command.

### -param unnamedParam4

Size of the execution parameters for the meta-command, in bytes.

## -remarks

The meta-command initialize call must be executed at least once prior to any execute call being executed on the GPU timeline.

## -see-also

[**PFND3D12DDI_EXECUTE_META_COMMAND_0052**](nc-d3d12umddi-pfnd3d12ddi_execute_meta_command_0052.md)
