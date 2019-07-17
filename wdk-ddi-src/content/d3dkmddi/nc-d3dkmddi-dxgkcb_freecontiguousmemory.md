---
UID: NC:d3dkmddi.DXGKCB_FREECONTIGUOUSMEMORY
title: DXGKCB_FREECONTIGUOUSMEMORY (d3dkmddi.h)
description: Implemented by the client driver to release a range of physically contiguous memory that was allocated by DXGKCB_ALLOCATECONTIGUOUSMEMORY.
ms.assetid: da301608-4cfa-4247-9f91-84a633ab87af
ms.date: 10/19/2018
ms.topic: callback
f1_keywords:
 - "d3dkmddi/DXGKCB_FREECONTIGUOUSMEMORY"
req.header: d3dkmddi.h
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
- d3dkmddi.h
api_name:
- DXGKCB_FREECONTIGUOUSMEMORY
product: 
- Windows
targetos: Windows
tech.root: display
---

# DXGKCB_FREECONTIGUOUSMEMORY callback function

## -description

Implemented by the client driver to release a range of physically contiguous memory that was allocated by [DXGKCB_ALLOCATECONTIGUOUSMEMORY](nc-d3dkmddi-dxgkcb_allocatecontiguousmemory.md).

## -prototype

```cpp
//Declaration

DXGKCB_FREECONTIGUOUSMEMORY DxgkcbFreecontiguousmemory;

// Definition

NTSTATUS DxgkcbFreecontiguousmemory
(
	IN_CONST_HANDLE hAdapter
	IN_CONST_PDXGKARGCB_FREECONTIGUOUSMEMORY pFreeContiguousMemory
)
{...}

DXGKCB_FREECONTIGUOUSMEMORY


```

## -parameters

### -param hAdapter

Handle to a display adapter.

### -param pFreeContiguousMemory

Pointer to a DXGKARGCB_FREECONTIGUOUSMEMORY structure that contains a handle to contiguous memory.

## -returns

Return STATUS_SUCCESS if the operation succeeds. Otherwise, return an appropriate NTSTATUS Values error code.

## -remarks

Register your implementation of this callback function by setting the appropriate member of PDXGKARGCB_FREECONTIGUOUSMEMORY and then calling DxgkCbFreeContiguousMemory.


## -see-also
