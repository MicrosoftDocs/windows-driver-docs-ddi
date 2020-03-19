---
UID: NC:d3dkmddi.DXGKCB_ALLOCATEPAGESFORMDL
title: DXGKCB_ALLOCATEPAGESFORMDL (d3dkmddi.h)
description: Implemented by the client driver to allocate physical memory pages for a memory descriptor list (MDL) from the GPU to the IoMmu's logical address space.
ms.assetid: fcfd09f8-109f-4123-9090-dc4ca89a6513
ms.date: 10/19/2018
keywords: ["DXGKCB_ALLOCATEPAGESFORMDL callback function"]
f1_keywords:
 - "d3dkmddi/DXGKCB_ALLOCATEPAGESFORMDL"
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
- DXGKCB_ALLOCATEPAGESFORMDL
product: 
- Windows
targetos: Windows
tech.root: display
---

# DXGKCB_ALLOCATEPAGESFORMDL callback function

## -description

Implemented by the client driver to allocate physical memory pages for a memory descriptor list (MDL) from the GPU to the IoMmu's logical address space. This callback function is a Windows graphics port driver function equivalent to the [MmAllocatePagesForMdl function](../wdm/nf-wdm-mmallocatepagesformdl.md) of the kernel mode driver.

## -prototype

```cpp
//Declaration

DXGKCB_ALLOCATEPAGESFORMDL DxgkcbAllocatepagesformdl;

// Definition

NTSTATUS DxgkcbAllocatepagesformdl
(
	IN_CONST_HANDLE hAdapter
	INOUT_PDXGKARGCB_ALLOCATEPAGESFORMDL pAllocatePagesForMdl
)
{...}

DXGKCB_ALLOCATEPAGESFORMDL


```

## -parameters

### -param hAdapter

A handle to the display adapter.

### -param pAllocatePagesForMdl

Pointer to a [DXGKARGCB_ALLOCATEPAGESFORMDL](ns-d3dkmddi-_dxgkargcb_allocatepagesformdl.md) structure that contains arguments to allocate pages for MDL.

## -returns

Return STATUS_SUCCESS if the operation succeeds. Otherwise, return an appropriate NTSTATUS Values error code.

## -remarks

Register your implementation of this callback function by setting the appropriate member of DXGKARGCB_ALLOCATEPAGESFORMDL and then calling DxgkCbAllocatePagesForMdl.

All memory accessed by the GPU during paging operations, or mapped via the GpuMmu must be mapped to the IoMmu. The Dxgkrnl provides callbacks to the KMD to allow the allocation and remapping in one step.

> [!NOTE] 
> Calls to DxgkCbAllocatePagesForMdl are limited to the 4GB PAGE_SIZE MDL restriction, and DirectX graphics kernel always specifies the *MM_ALLOCATE_FULLY_REQUIRED* flag in the internal call to [MmAllocatePagesForMdlEx function](../wdm/nf-wdm-mmallocatepagesformdl.md). The driver should also not lock any memory. Dxgkrnl will manage locked pages for the driver, and once the memory is remapped, the logical address of the pages provided to the driver may no longer match the physical addresses.





## -see-also
