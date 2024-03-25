---
UID: NS:d3d12umddi.D3D12DDIARG_META_COMMAND_PARAMETER_DESC
title: D3D12DDIARG_META_COMMAND_PARAMETER_DESC (d3d12umddi.h)
description: Learn more about the D3D12DDIARG_META_COMMAND_PARAMETER_DESC structure.
ms.date: 12/12/2023
keywords: ["D3D12DDIARG_META_COMMAND_PARAMETER_DESC structure"]
ms.keywords: D3D12DDIARG_META_COMMAND_PARAMETER_DESC, D3D12DDIARG_META_COMMAND_PARAMETER_DESC,
req.header: d3d12umddi.h
req.include-header: 
req.target-type: 
req.target-min-winverclnt: Windows 10, version 1809
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.lib: 
req.dll: 
req.ddi-compliance: 
req.unicode-ansi: 
req.max-support: 
req.typenames: D3D12DDIARG_META_COMMAND_PARAMETER_DESC
targetos: Windows
tech.root: display
ms.custom: RS5
f1_keywords:
 - D3D12DDIARG_META_COMMAND_PARAMETER_DESC
 - d3d12umddi/D3D12DDIARG_META_COMMAND_PARAMETER_DESC
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - d3d12umddi.h
api_name:
 - D3D12DDIARG_META_COMMAND_PARAMETER_DESC
dev_langs:
 - c++
---

# D3D12DDIARG_META_COMMAND_PARAMETER_DESC structure

## -description

**D3D12DDIARG_META_COMMAND_PARAMETER_DESC** contains the meta-command parameter descriptions.

## -struct-fields

### -field Name

The name of the meta-command parameter.

### -field Type

A [**D3D12DDI_META_COMMAND_PARAMETER_TYPE**] value that indicates the type of meta-command parameter.

### -field Flags

A [**D3D12DDI_META_COMMAND_PARAMETER_FLAGS**] value that indicate whether the resource is used for input or output.

### -field RequiredResourceState

A [**D3D12DDI_RESOURCE_STATES**](ne-d3d12umddi-d3d12ddi_resource_states.md) value that indicates the expected state of the resource. This is specified for each resource in the meta-command definition.

## -remarks

The debug layer validates the type and state to ensure the parameters supplied during creation are set up correctly.

The driver reports the list of parameters and their type and the runtime calculates a 4-byte aligned offset in a structure that the user developer passes these parameters in.

## -see-also

[**PFND3D12DDI_ENUMERATE_META_COMMAND_PARAMETERS_0052**](nc-d3d12umddi-pfnd3d12ddi_enumerate_meta_command_parameters_0052.md)
