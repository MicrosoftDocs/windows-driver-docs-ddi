---
UID: NC:d3d12umddi.PFND3D12DDI_ENUMERATE_META_COMMAND_PARAMETERS_0052
title: PFND3D12DDI_ENUMERATE_META_COMMAND_PARAMETERS_0052 (d3d12umddi.h)
description: Enumerates meta-command parameters.
ms.assetid: 3808a357-1a5b-4239-9dde-6f7b07212a91
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
targetos: Windows
tech.root: display
ms.custom: RS5
f1_keywords:
 - "d3d12umddi/PFND3D12DDI_ENUMERATE_META_COMMAND_PARAMETERS_0052"
topic_type:
 - apiref
api_type:
 - UserDefined
api_location:
 - d3d12umddi.h
api_name:
 - PFND3D12DDI_ENUMERATE_META_COMMAND_PARAMETERS_0052
product:
 - Windows
dev_langs:
 - c++
---

# PFND3D12DDI_ENUMERATE_META_COMMAND_PARAMETERS_0052 callback function

## -description

Enumerates meta-command parameters.

## -parameters

### -param Arg1

A handle to the display device (graphics context).

### -param CommandId

The command id.

### -param Stage

A [D3D12DDI_META_COMMAND_PARAMETER_STAGE](ne-d3d12umddi-d3d12ddi_meta_command_parameter_stage.md).

### -param pParameterCount

The number of meta-command paramters.

### -param pParameterDescs

Pointer to an meta-command descriptions.

## -returns

Returns HRESULT.

## -prototype

```cpp
//Declaration

PFND3D12DDI_ENUMERATE_META_COMMAND_PARAMETERS_0052 Pfnd3d12ddiEnumerateMetaCommandParameters0052; 

// Definition

HRESULT Pfnd3d12ddiEnumerateMetaCommandParameters0052 
(
	D3D12DDI_HDEVICE Arg1
	GUID CommandId
	D3D12DDI_META_COMMAND_PARAMETER_STAGE Stage
	UINT *pParameterCount
	D3D12DDIARG_META_COMMAND_PARAMETER_DESC *pParameterDescs
)
{...}

```

## -remarks

## -see-also

