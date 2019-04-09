---
UID: NC:d3dkmddi.DXGKCB_ALLOCATECONTIGUOUSMEMORY
title: DXGKCB_ALLOCATECONTIGUOUSMEMORY (d3dkmddi.h)
description: Implemented by the client driver to allocate contiguous memory regions in the IoMMu's logical address space.
ms.assetid: 58a963a4-c65e-4ac5-bdeb-583604dbec2e
ms.date: 10/19/2018
ms.topic: callback
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
- DXGKCB_ALLOCATECONTIGUOUSMEMORY
product: 
- Windows
targetos: Windows
tech.root: display
---

# DXGKCB_ALLOCATECONTIGUOUSMEMORY callback function

## -description

Implemented by the client driver to allocate contiguous memory regions in the IoMMu's logical address space. This callback function is a Windows graphics port driver function equivalent to the [MmAllocateContiguousMemory function](../wdm/nf-wdm-mmallocatecontiguousmemory.md) of the kernel mode driver.

## -prototype

```cpp
//Declaration

DXGKCB_ALLOCATECONTIGUOUSMEMORY DxgkcbAllocatecontiguousmemory;

// Definition

NTSTATUS DxgkcbAllocatecontiguousmemory
(
	IN_CONST_HANDLE hAdapter
	INOUT_PDXGKARGCB_ALLOCATECONTIGUOUSMEMORY pAllocateContiguousMemory
)
{...}

DXGKCB_ALLOCATECONTIGUOUSMEMORY


```

## -parameters

### -param hAdapter

Handle to a display adapter.

### -param pAllocateContiguousMemory

Pointer to a [DXGKARGCB_ALLOCATECONTIGUOUSMEMORY](ns-d3dkmddi-_dxgkargcb_allocatecontiguousmemory.md) structure that contains arguments to allocate contiguous memory.

## -returns

Return STATUS_SUCCESS if the operation succeeds. Otherwise, return an appropriate NTSTATUS Values error code.

## -remarks

Register your implementation of this callback function by setting the appropriate members of DXGKARGCB_ALLOCATECONTIGUOUSMEMORY and then calling DxgkCbAllocateContiguousMemory.

All memory accessed by the GPU during paging operations, or mapped via the GpuMmu must be mapped to the IoMmu. The Dxgkrnl provides callbacks to the KMD to allow the allocation and remapping in one step.

>**Note** The driver should not lock any memory. Dxgkrnl will manage locked pages for the driver, and once the memory is remapped, the logical address of the pages provided to the driver may no longer match the physical addresses.

## -see-also
