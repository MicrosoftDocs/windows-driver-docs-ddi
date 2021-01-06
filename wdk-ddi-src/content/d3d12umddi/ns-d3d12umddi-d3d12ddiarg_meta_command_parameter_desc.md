---
UID: NS:d3d12umddi.D3D12DDIARG_META_COMMAND_PARAMETER_DESC
title: D3D12DDIARG_META_COMMAND_PARAMETER_DESC (d3d12umddi.h)
description: Meta-command parameter descriptions.
ms.date: 10/19/2018
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

Meta-command parameter descriptions.

## -struct-fields

### -field Name

The name of the meta-command parameter.

### -field Type

The type of meta-command parameter, such as float or UINT64.

### -field Flags

Flags that indicate whether the resource is used for input or output.

### -field RequiredResourceState

 
Resources that indicate the expected state of the resource. This is specified for each resource in the meta-command definition.

## -remarks

The type and state will be validated by the debug layer to ensure the parameters supplied during creation are setup correctly.

The driver will report the list of parameters and their type and the runtime will calculate a 4-byte aligned offset in a struct the user developer will pass these parameters in.

## -see-also

