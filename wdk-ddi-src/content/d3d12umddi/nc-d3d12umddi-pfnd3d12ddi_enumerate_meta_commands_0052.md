---
UID: NC:d3d12umddi.PFND3D12DDI_ENUMERATE_META_COMMANDS_0052
title: PFND3D12DDI_ENUMERATE_META_COMMANDS_0052 (d3d12umddi.h)
description: The PFND3D12DDI_ENUMERATE_META_COMMANDS_0052 callback function enumerates meta-commands.
ms.date: 10/19/2018
keywords: ["PFND3D12DDI_ENUMERATE_META_COMMANDS_0052 callback function"]
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
 - PFND3D12DDI_ENUMERATE_META_COMMANDS_0052
 - d3d12umddi/PFND3D12DDI_ENUMERATE_META_COMMANDS_0052
topic_type:
 - apiref
api_type:
 - UserDefined
api_location:
 - d3d12umddi.h
api_name:
 - PFND3D12DDI_ENUMERATE_META_COMMANDS_0052
dev_langs:
 - c++
---

# PFND3D12DDI_ENUMERATE_META_COMMANDS_0052 callback function

## -description

The **PFND3D12DDI_ENUMERATE_META_COMMANDS_0052** callback function enumerates meta-commands.

## -parameters

### -param unnamedParam1

A handle to the display device (graphics context).

### -param pNumMetaCommands

Pointer to a value in which the number of enumerated meta-commands is written.

### -param pDescs

Pointer to an array of [**D3D12DDIARG_META_COMMAND_DESC**](ns-d3d12umddi-d3d12ddiarg_meta_command_desc.md) structures containing the meta-command descriptions.

## -returns

Returns HRESULT.

## -see-also

[**PFND3D12DDI_CREATE_META_COMMAND_0052**](nc-d3d12umddi-pfnd3d12ddi_create_meta_command_0052.md)
