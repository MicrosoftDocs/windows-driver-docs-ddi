---
UID: NC:d3d12umddi.PFND3D12DDI_CHECKRESOURCEALLOCATIONINFO_0003
title: PFND3D12DDI_CHECKRESOURCEALLOCATIONINFO_0003 (d3d12umddi.h)
description: The pfnCheckResourceAllocationInfo callback function supports checking resource allocation information.
ms.assetid: 88c3cb14-acf1-4391-a8f0-059a2533a183
ms.date: 10/19/2018
ms.topic: callback
f1_keywords:
 - "d3d12umddi/PFND3D12DDI_CHECKRESOURCEALLOCATIONINFO_0003"
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
- apiref
api_type: 
- UserDefined
api_location: 
- d3d12umddi.h
api_name: 
- PFND3D12DDI_CHECKRESOURCEALLOCATIONINFO_0003
product: 
- Windows
targetos: Windows
tech.root: display
ms.custom: RS5
---

# PFND3D12DDI_CHECKRESOURCEALLOCATIONINFO_0003 callback function

## -description

The pfnCheckResourceAllocationInfo callback function supports checking resource allocation information.

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

## -parameters

### -param D3D12DDI_HDEVICE  

A handle to the display device (graphics context).
 
### -param * 

Pointer to a D3D12DDIARG_CREATERESOURCE_0003 structure.

### -param D3D12DDI_RESOURCE_OPTIMIZATION_FLAGS

Resource optimization flags.

### -param AlignmentRestriction

Indicates alignment restriction.

### -param VisibleNodeMask

Indicates the visible node mask.

### -param * 

Pointer to a D3D12DDI_RESOURCE_ALLOCATION_INFO structure.

## -returns

Returns VOID.
