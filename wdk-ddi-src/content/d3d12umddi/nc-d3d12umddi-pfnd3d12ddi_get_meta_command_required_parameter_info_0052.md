---
UID: NC:d3d12umddi.PFND3D12DDI_GET_META_COMMAND_REQUIRED_PARAMETER_INFO_0052
title: PFND3D12DDI_GET_META_COMMAND_REQUIRED_PARAMETER_INFO_0052
author: windows-driver-content
description: Gets required information for a meta-command.
ms.assetid: 0056ecd5-aaa6-435e-9812-a88dc5ef27ab
ms.date: 10/19/2018
ms.topic: callback
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
topic_type: 
-	apiref
api_type: 
-	UserDefined
api_location: 
-	d3d12umddi.h
api_name: 
-	PFND3D12DDI_GET_META_COMMAND_REQUIRED_PARAMETER_INFO_0052
product:
-	Windows
targetos: Windows
tech.root: display
ms.custom: RS5
---

# PFND3D12DDI_GET_META_COMMAND_REQUIRED_PARAMETER_INFO_0052 callback function

## -description

Gets required information for a meta-command.

## -prototype

```cpp
//Declaration

PFND3D12DDI_GET_META_COMMAND_REQUIRED_PARAMETER_INFO_0052 Pfnd3d12ddiGetMetaCommandRequiredParameterInfo0052; 

// Definition

VOID Pfnd3d12ddiGetMetaCommandRequiredParameterInfo0052 
(
	D3D12DDI_HMETACOMMAND_0052 Arg1
	D3D12DDI_META_COMMAND_PARAMETER_STAGE Stage
	UINT ParameterIndex
	D3D12DDIARG_META_COMMAND_REQUIRED_PARAMETER_INFO *
)
{...}

```

## -parameters

### -param Arg1

A handle to a meta-command.

### -param Stage

A pointer to a [D3D12DDI_META_COMMAND_PARAMETER_STAGE](ne-d3d12umddi-d3d12ddi_meta_command_parameter_stage.md).

### -param ParameterIndex

The index of the parameter.

### -param *: 

A pointer to a [D3D12DDIARG_METACOMMAND_REQUIRED_PARAMETER_INFO](ns-d3d12umddi-d3d12ddiarg_metacommand_required_parameter_info.md) structure that contains the meta-command's required parameter info.

## -returns

Returns VOID.

## -remarks



## -see-also
