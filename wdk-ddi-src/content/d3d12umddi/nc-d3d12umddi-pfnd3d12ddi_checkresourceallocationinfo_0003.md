---
UID: NC:d3d12umddi.PFND3D12DDI_CHECKRESOURCEALLOCATIONINFO_0003
title: PFND3D12DDI_CHECKRESOURCEALLOCATIONINFO_0003 (d3d12umddi.h)
description: The PFND3D12DDI_CHECKRESOURCEALLOCATIONINFO_0003 callback function checks resource allocation information.
ms.date: 05/24/2022
keywords: ["PFND3D12DDI_CHECKRESOURCEALLOCATIONINFO_0003 callback function"]
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
targetos: Windows
tech.root: display
ms.custom: RS5
f1_keywords:
 - PFND3D12DDI_CHECKRESOURCEALLOCATIONINFO_0003
 - d3d12umddi/PFND3D12DDI_CHECKRESOURCEALLOCATIONINFO_0003
topic_type:
 - apiref
api_type:
 - UserDefined
api_location:
 - d3d12umddi.h
api_name:
 - PFND3D12DDI_CHECKRESOURCEALLOCATIONINFO_0003
product:
 - Windows
dev_langs:
 - c++
---

# PFND3D12DDI_CHECKRESOURCEALLOCATIONINFO_0003 callback function

## -description

The **PFND3D12DDI_CHECKRESOURCEALLOCATIONINFO_0003** callback function supports checking resource allocation information.

## -parameters

### -param unnamedParam1  

[in] A handle to the display device (graphics context).

### -param unnamedParam2

[in] Pointer to a D3D12DDIARG_CREATERESOURCE_0003 structure.

### -param unnamedParam3

Resource optimization flags.

### -param AlignmentRestriction

Indicates alignment restriction.

### -param VisibleNodeMask

Indicates the visible node mask.

### -param unnamedParam6

[out] Pointer to a D3D12DDI_RESOURCE_ALLOCATION_INFO structure.

## -prototype

```cpp
//Declaration

PFND3D12DDI_CHECKRESOURCEALLOCATIONINFO_0003 Pfnd3d12ddiCheckresourceallocationinfo0003; 

// Definition

VOID Pfnd3d12ddiCheckresourceallocationinfo0003 
(
	 D3D12DDI_HDEVICE
	CONST D3D12DDIARG_CREATERESOURCE_0003 *
	 D3D12DDI_RESOURCE_OPTIMIZATION_FLAGS
	UINT64 AlignmentRestriction
	UINT VisibleNodeMask
	D3D12DDI_RESOURCE_ALLOCATION_INFO *
)
{...}

PFND3D12DDI_CHECKRESOURCEALLOCATIONINFO_0003 


```
