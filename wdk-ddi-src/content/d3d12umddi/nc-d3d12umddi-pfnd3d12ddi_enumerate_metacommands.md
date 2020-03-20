---
UID: NC:d3d12umddi.PFND3D12DDI_ENUMERATE_METACOMMANDS
title: PFND3D12DDI_ENUMERATE_METACOMMANDS (d3d12umddi.h)
description: The PFND3D12DDI_ENUMERATE_METACOMMANDS callback function enumerates meta-commands.
ms.assetid: df59aa62-ee03-4ec3-bcab-8a50ef26a03b
ms.date: 10/19/2018
keywords: ["PFND3D12DDI_ENUMERATE_METACOMMANDS callback function"]
f1_keywords:
 - "d3d12umddi/PFND3D12DDI_ENUMERATE_METACOMMANDS"
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
req.max-support: Windows 10, version 1803
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
- PFND3D12DDI_ENUMERATE_METACOMMANDS
product: 
- Windows
targetos: Windows
tech.root: display
---

# PFND3D12DDI_ENUMERATE_METACOMMANDS callback function

## -description

The PFND3D12DDI_ENUMERATE_METACOMMANDS callback function enumerates meta-commands.

## -prototype

```cpp
//Declaration

PFND3D12DDI_ENUMERATE_METACOMMANDS Pfnd3d12ddiEnumerateMetacommands;

// Definition

HRESULT Pfnd3d12ddiEnumerateMetacommands
(
	 D3D12DDI_HDEVICE
	UINT *pNumMetaCommands
	D3D12DDIARG_METACOMMAND_DESCRIPTION *pDescs
)
{...}

PFND3D12DDI_ENUMERATE_METACOMMANDS


```

## -parameters

### -param D3D12DDI_HDEVICE

A handle to the display device (graphics context).

### -param pNumMetaCommands

The number of meta-commands.

### -param pDescs:

Pointer to an array of meta-command descriptions.

## -returns

Returns STATUS_SUCCESS if completed successfully.

