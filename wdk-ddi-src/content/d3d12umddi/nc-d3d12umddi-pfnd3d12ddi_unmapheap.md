---
UID: NC:d3d12umddi.PFND3D12DDI_UNMAPHEAP
title: PFND3D12DDI_UNMAPHEAP (d3d12umddi.h)
description: A client driver implements PFND3D12DDI_UNMAPHEAP to unmap a heap.
ms.assetid: ff2743ac-ae14-4c19-836a-d8a869b3ff9b
ms.date: 08/21/2020
keywords: ["PFND3D12DDI_UNMAPHEAP callback function"]
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
 - PFND3D12DDI_UNMAPHEAP
 - d3d12umddi/PFND3D12DDI_UNMAPHEAP
topic_type:
 - apiref
api_type:
 - UserDefined
api_location:
 - d3d12umddi.h
api_name:
 - PFND3D12DDI_UNMAPHEAP
product:
 - Windows
dev_langs:
 - c++
---

# PFND3D12DDI_UNMAPHEAP callback function


## -description

A client driver implements **PFND3D12DDI_UNMAPHEAP** to unmap a heap.

## -parameters

### -param Arg1

[in] *hDisplayDevice*: Handle to the display device (graphics context).

### -param Arg2

[in] *hHeap*: Handle to a display device-managed heap that needs to be unmapped.

## -prototype

```cpp
//Declaration

PFND3D12DDI_UNMAPHEAP Pfnd3d12ddiUnmapheap;

// Definition

VOID Pfnd3d12ddiUnmapheap
(
    D3D12DDI_HDEVICE hDisplayDevice,
    D3D12DDI_HHEAP hHeap
)
{...}

PFND3D12DDI_UNMAPHEAP

```

## -remarks

## -see-also

[**PFND3D12DDI_MAPHEAP**](nc-d3d12umddi-pfnd3d12ddi_mapheap.md)

