---
UID: NC:d3d12umddi.PFND3D12DDI_SET_ROOT_SIGNATURE
title: PFND3D12DDI_SET_ROOT_SIGNATURE (d3d12umddi.h)
description: Sets the root signature.
ms.date: 10/19/2018
keywords: ["PFND3D12DDI_SET_ROOT_SIGNATURE callback function"]
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
ms.custom: RS5
tech.root: display
f1_keywords:
 - PFND3D12DDI_SET_ROOT_SIGNATURE
 - d3d12umddi/PFND3D12DDI_SET_ROOT_SIGNATURE
topic_type:
 - apiref
api_type:
 - UserDefined
api_location:
 - d3d12umddi.h
api_name:
 - PFND3D12DDI_SET_ROOT_SIGNATURE
dev_langs:
 - c++
---

# PFND3D12DDI_SET_ROOT_SIGNATURE callback function


## -description

Sets the root signature.

## -parameters

### -param Arg1

A handle to a command list.

### -param Arg2

A handle to a root signature.

## -prototype

```cpp
//Declaration

PFND3D12DDI_SET_ROOT_SIGNATURE Pfnd3d12ddiSetRootSignature; 

// Definition

VOID Pfnd3d12ddiSetRootSignature 
(
	D3D12DDI_HCOMMANDLIST Arg1
	D3D12DDI_HROOTSIGNATURE Arg2
)
{...}

```

## -remarks

## -see-also

