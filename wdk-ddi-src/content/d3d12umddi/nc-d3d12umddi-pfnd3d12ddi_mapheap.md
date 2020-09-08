---
UID: NC:d3d12umddi.PFND3D12DDI_MAPHEAP
title: PFND3D12DDI_MAPHEAP (d3d12umddi.h)
description: A client driver implements PFND3D12DDI_MAPHEAP to map a heap.
ms.assetid: 2187b018-e5d2-4a82-8232-ba9f1ae3a988
ms.date: 08/21/2020
keywords: ["PFND3D12DDI_MAPHEAP callback function"]
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
 - PFND3D12DDI_MAPHEAP
 - d3d12umddi/PFND3D12DDI_MAPHEAP
topic_type:
 - apiref
api_type:
 - UserDefined
api_location:
 - d3d12umddi.h
api_name:
 - PFND3D12DDI_MAPHEAP
product:
 - Windows
dev_langs:
 - c++
---

# PFND3D12DDI_MAPHEAP callback function


## -description

A client driver implements **PFND3D12DDI_MAPHEAP** to map a heap.

## -parameters

### -param Arg1

[in] *hDisplayDevice*: Handle to the display device (graphics context).

### -param Arg2

[in] *hHeap*: Handle to a display device-managed heap that needs to be mapped.

### -param Arg3

[out] *ppData**: A pointer to the mapped heap data.

## -returns

**PFND3D12DDI_MAPHEAP** returns S_OK on success. It should return an appropriate HRESULT error code on failure.

## -prototype

```cpp
//Declaration

PFND3D12DDI_MAPHEAP Pfnd3d12ddiMapheap;

// Definition

HRESULT Pfnd3d12ddiMapheap
(
    D3D12DDI_HDEVICE hDisplayDevice,
    D3D12DDI_HHEAP hHeap,
    VOID **ppData
)
{...}

PFND3D12DDI_MAPHEAP

```

## -remarks

Heap data is typically accessible to the GPU only. **PFND3D12DDI_MAPHEAP** makes the heap data accessible to the CPU. The driver should map the heap data and return a CPU-accessible pointer in *ppData*.

## -see-also

[**PFND3D12DDI_UNMAPHEAP**](nc-d3d12umddi-pfnd3d12ddi_unmapheap.md)

