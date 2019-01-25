---
UID: NC:d3d12umddi.PFND3D12DDI_PRESENT_0051
title: PFND3D12DDI_PRESENT_0051 (d3d12umddi.h)
description: The PFND3D12DDI_PRESENT_0051 callback function copies content from source allocations to a primary surface.
ms.assetid: 191033a4-5f8c-409b-9097-a9f096267844
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
-	apiref
api_type: 
-	UserDefined
api_location: 
-	d3d12umddi.h
api_name: 
-	PFND3D12DDI_PRESENT_0051
product:
-	Windows
targetos: Windows
tech.root: display
ms.custom: RS5
---

# PFND3D12DDI_PRESENT_0051 callback function

## -description

The PFND3D12DDI_PRESENT_0051 callback function copies content from source allocations to a primary surface (and sometimes to off-screen system memory allocations).

## -prototype

```cpp
//Declaration

PFND3D12DDI_PRESENT_0051 Pfnd3d12ddiPresent0051; 

// Definition

VOID Pfnd3d12ddiPresent0051 
(
	D3D12DDI_HCOMMANDLIST Arg1
	D3D12DDI_HCOMMANDQUEUE Arg2
	CONST D3D12DDIARG_PRESENT_0001 *
	D3D12DDI_PRESENT_0051 *
	D3D12DDI_PRESENT_CONTEXTS_0051 *
	D3D12DDI_PRESENT_HWQUEUES_0051 *
)
{...}

```

## -parameters

### -param Arg1

A handle to the driver's data for the command list.

### -param Arg2

A handle the driver's data for the command queue.

### -param *

Pointer to a [D3D12DDIARG_PRESENT_0001](ns-d3d12umddi-d3d12ddiarg_present_0001.md) structure that contains arguments.

### -param *

Pointer to a [D3D12DDI_PRESENT_0051](ns-d3d12umddi-d3d12ddi_present_0051.md) structure that contains arguments for this callback.

### -param *

Pointer to a [D3D12DDI_PRESENT_CONTEXTS_0051](ns-d3d12umddi-d3d12ddi_present_contexts_0051.md) structure.

### -param *

Pointer to a [D3D12DDI_PRESENT_HWQUEUES_0051](ns-d3d12umddi-d3d12ddi_present_hwqueues_0051.md) structure.



## -returns

Returns VOID.

## -remarks

The PFND3D12DDI_PRESENT_0051 callback function split the output arguments into ones that are relevant for the command queue involved. For software scheduled command queues, the driver provides contexts. For hardware scheduled command queues, the driver provides hardware queues.


## -see-also
