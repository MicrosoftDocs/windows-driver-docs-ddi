---
UID: NC:d3d12umddi.PFND3D12DDI_RS_SET_SHADING_RATE_0062
title: PFND3D12DDI_RS_SET_SHADING_RATE_0062
author: windows-driver-content
description: Sets the command-level shading rate and combiners.
tech.root: display
ms.assetid: 4bae80db-d024-4820-a82b-3b06730e5426
ms.author: windowsdriverdev
ms.date: 04/04/2019
ms.topic: callback
req.header: d3d12umddi.h
req.include-header:
req.target-type:
req.target-min-winverclnt: Windows 10, version 1903
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
 - PFND3D12DDI_RS_SET_SHADING_RATE_0062
product:
- Windows
targetos: Windows
ms.custom: D3D12 Release 6, Build rev 2., 19H1
---

# PFND3D12DDI_RS_SET_SHADING_RATE_0062 callback function

## -description

Sets the command-level shading rate and combiners.

## -prototype

```
//Declaration

PFND3D12DDI_RS_SET_SHADING_RATE_0062 Pfnd3d12ddiRsSetShadingRate0062; 

// Definition

VOID Pfnd3d12ddiRsSetShadingRate0062 
(
	D3D12DDI_HCOMMANDLIST Arg1
	D3D12DDI_SHADING_RATE_0062 ShadingRate
	const D3D12DDI_SHADING_RATE_COMBINER_0062 *Combiners
)
{...}

```

## -parameters

### -param Arg1

A handle to the command list.

### -param ShadingRate

A [D3D12DDI_SHADING_RATE_0062](ne-d3d12umddi-d3d12ddi_shading_rate_0062.md) enum that indicates the shading rate.

### -param *Combiners

Pointer to a [D3D12DDI_SHADING_RATE_COMBINER_0062](ne-d3d12umddi-d3d12ddi_shading_rate_combiner_0062.md) enum that indicates the combined shading rate.

## -returns

Returns VOID.

## -remarks

The shading rate, and optionally, combiners, are specified through a command list method.

## -see-also
