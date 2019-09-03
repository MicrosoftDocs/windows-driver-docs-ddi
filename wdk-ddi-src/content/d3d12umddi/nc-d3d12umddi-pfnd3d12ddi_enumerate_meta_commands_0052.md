---
UID: NC:d3d12umddi.PFND3D12DDI_ENUMERATE_META_COMMANDS_0052
title: PFND3D12DDI_ENUMERATE_META_COMMANDS_0052 (d3d12umddi.h)
description: The PFND3D12DDI_ENUMERATE_META_COMMANDS_0052 callback function enumerates meta-commands.
ms.assetid: fdf5f76e-4486-4058-beaf-1ebefe65246a
ms.date: 10/19/2018
ms.topic: callback
f1_keywords:
 - "d3d12umddi/PFND3D12DDI_ENUMERATE_META_COMMANDS_0052"
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
- apiref
api_type: 
- UserDefined
api_location: 
- d3d12umddi.h
api_name: 
- PFND3D12DDI_ENUMERATE_META_COMMANDS_0052
product:
- Windows
targetos: Windows
tech.root: display
dev_langs:
 - c++
ms.custom: RS5
---

# PFND3D12DDI_ENUMERATE_META_COMMANDS_0052 callback function

## -description

The PFND3D12DDI_ENUMERATE_META_COMMANDS_0052 callback function enumerates meta-commands.

## -prototype

```cpp
//Declaration

PFND3D12DDI_ENUMERATE_META_COMMANDS_0052 Pfnd3d12ddiEnumerateMetaCommands0052; 

// Definition

HRESULT Pfnd3d12ddiEnumerateMetaCommands0052 
(
	D3D12DDI_HDEVICE Arg1
	UINT *pNumMetaCommands
	D3D12DDIARG_META_COMMAND_DESC *pDescs
)
{...}

```

## -parameters

### -param Arg1

A handle to the display device (graphics context).

### -param *pNumMetaCommands

The number of meta-commands.

### -param *pDescs

Pointer to an array of meta-command descriptions.

## -returns

Returns HRESULT.

## -remarks




## -see-also
