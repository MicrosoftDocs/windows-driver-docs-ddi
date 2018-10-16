---
UID: NC:d3d12umddi.PFND3D12DDI_ENUMERATE_METACOMMAND_SIGNATURE
title: PFND3D12DDI_ENUMERATE_METACOMMAND_SIGNATURE
author: windows-driver-content
description: Implemented by the client driver to enumerate meta-command signatures.
ms.assetid: 9ab6bbb3-6641-4576-b86d-f90dd2975cb0
ms.author: windowsdriverdev
ms.date:
ms.topic: callback
ms.prod: windows-hardware
ms.technology: windows-devices
req.header: d3d12umddi.h
req.include-header:
req.target-type:
req.target-min-winverclnt:
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
-	PFND3D12DDI_ENUMERATE_METACOMMAND_SIGNATURE
product: 
- Windows
targetos: Windows
tech.root: display
---

# PFND3D12DDI_ENUMERATE_METACOMMAND_SIGNATURE callback function

## -description

Implemented by the client driver to enumerate meta-command signatures.

## -prototype

```cpp
//Declaration

PFND3D12DDI_ENUMERATE_METACOMMAND_SIGNATURE Pfnd3d12ddiEnumerateMetacommandSignature;

// Definition

HRESULT Pfnd3d12ddiEnumerateMetacommandSignature
(
	 D3D12DDI_HDEVICE
	GUID CommandId
	UINT SignatureId
	UINT *pParameterCount
	D3D12DDIARG_METACOMMAND_PARAMETER_DESC *pParameterDescs
)
{...}

PFND3D12DDI_ENUMERATE_METACOMMAND_SIGNATURE


```

## -parameters

### -param D3D12DDI_HDEVICE

A handle to the display device (graphics context).

### -param CommandId

The command identifier.

### -param SignatureId

The command signature id.

### -param *pParameterCount

The count of meta-commands.

### -param *pParameterDescs:

The description of meta-commands.

## -returns

Returns STATUS_SUCCESS if completed successfully.
