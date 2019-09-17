---
UID: NC:d3d12umddi.PFND3D12DDI_RS_SET_SHADING_RATE_IMAGE_0062
title: PFND3D12DDI_RS_SET_SHADING_RATE_IMAGE_0062
author: windows-driver-content
description: Sets the screen space image.
tech.root: display
ms.assetid: b2cb2d40-f60a-4896-b590-af1faac305b4
ms.author: windowsdriverdev
ms.date: 04/04/2019
ms.topic: callback
f1_keywords:
 - "d3d12umddi/PFND3D12DDI_RS_SET_SHADING_RATE_IMAGE_0062"
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
 - PFND3D12DDI_RS_SET_SHADING_RATE_IMAGE_0062
product:
- Windows
targetos: Windows
dev_langs:
 - c++
ms.custom: D3D12 Release 6, Build rev 2., 19H1
---

# PFND3D12DDI_RS_SET_SHADING_RATE_IMAGE_0062 callback function

## -description

Sets the screen space image.

## -prototype

```
//Declaration

PFND3D12DDI_RS_SET_SHADING_RATE_IMAGE_0062 Pfnd3d12ddiRsSetShadingRateImage0062; 

// Definition

VOID Pfnd3d12ddiRsSetShadingRateImage0062 
(
	D3D12DDI_HCOMMANDLIST Arg1
	D3D12DDI_HRESOURCE hShadingRateImage
)
{...}

```

## -parameters

### -param Arg1

A handle to the command list.

### -param hShadingRateImage

A handle to the resource that contains the shading rate image.

## -returns

Returns VOID.

## -remarks


## -see-also
