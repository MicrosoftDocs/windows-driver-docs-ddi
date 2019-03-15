---
UID: NC:d3d12umddi.PFND3D12DDI_SET_ROOT_SIGNATURE
title: PFND3D12DDI_SET_ROOT_SIGNATURE (d3d12umddi.h)
description: Sets the root signature.
ms.assetid: 82e4e567-c176-4c16-ba6f-3f901a91f7ec
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
- apiref
api_type: 
- UserDefined
api_location: 
- d3d12umddi.h
api_name: 
- PFND3D12DDI_SET_ROOT_SIGNATURE
product:
- Windows
targetos: Windows
ms.custom: RS5
tech.root: display
---

# PFND3D12DDI_SET_ROOT_SIGNATURE callback function

## -description

Sets the root signature.

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

## -parameters

### -param Arg1

A handle to a command list.

### -param Arg2

A handle to a root signature.


## -returns

Returns VOID.

## -remarks




## -see-also
