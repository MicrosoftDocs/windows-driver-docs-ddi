---
UID: NC:d3d12umddi.PFND3D12DDI_INITIALIZE_METACOMMAND
title: PFND3D12DDI_INITIALIZE_METACOMMAND (d3d12umddi.h)
author: mimisasouvanh
ms.author: misaso
description: Implemented by the client driver to initialize a meta-command.
ms.assetid: a13ed485-4f5f-45fb-ba49-a2ea44ece8aa
ms.date: 10/19/2018
f1_keywords:
 - "d3d12umddi/PFND3D12DDI_INITIALIZE_METACOMMAND"
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
- PFND3D12DDI_INITIALIZE_METACOMMAND
product: 
- Windows
targetos: Windows
tech.root: display
---

# PFND3D12DDI_INITIALIZE_METACOMMAND callback function

## -description

Implemented by the client driver to initialize a meta-command.

## -prototype

```cpp
//Declaration

PFND3D12DDI_INITIALIZE_METACOMMAND Pfnd3d12ddiInitializeMetacommand;

// Definition

VOID Pfnd3d12ddiInitializeMetacommand
(
	 D3D12DDI_HCOMMANDLIST
	 D3D12DDI_HMETACOMMAND
	CONST D3D12DDIARG_METACOMMAND_PARAMETER_DATA *
	UINT NumParameters
)
{...}

PFND3D12DDI_INITIALIZE_METACOMMAND


```

## -parameters

### -param D3D12DDI_HCOMMANDLIST

A handle to the driver's data for the command list. The driver uses this region of memory to store internal data structures that are related to its command list.

### -param D3D12DDI_HMETACOMMAND

A handle to a meta-command.

### -param D3D12DDIARG_METACOMMAND_PARAMETER_DATA *

A pointer to a D3D12DDIARG_METACOMMAND_PARAMETER_DATA structure.

### -param NumParameters:

The number of parameters in the meta-command.

## -returns

This callback function does not return a value.

