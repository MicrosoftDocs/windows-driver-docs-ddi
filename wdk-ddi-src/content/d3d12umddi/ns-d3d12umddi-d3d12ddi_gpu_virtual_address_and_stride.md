---
UID: NS:d3d12umddi.D3D12DDI_GPU_VIRTUAL_ADDRESS_AND_STRIDE
title: D3D12DDI_GPU_VIRTUAL_ADDRESS_AND_STRIDE (d3d12umddi.h)
description: Describes the GPU virtual address and stride.
ms.assetid: 44028f01-8415-42b0-afd0-ac773f645eba
ms.date: 10/19/2018
keywords: ["D3D12DDI_GPU_VIRTUAL_ADDRESS_AND_STRIDE structure"]
f1_keywords:
 - "d3d12umddi/D3D12DDI_GPU_VIRTUAL_ADDRESS_AND_STRIDE"
 - "D3D12DDI_GPU_VIRTUAL_ADDRESS_AND_STRIDE"
ms.keywords: D3D12DDI_GPU_VIRTUAL_ADDRESS_AND_STRIDE, D3D12DDI_GPU_VIRTUAL_ADDRESS_AND_STRIDE, 
req.header: d3d12umddi.h
req.include-header:
req.target-type:
req.target-min-winverclnt: Windows 10, version 1809
req.target-min-winversvr:
req.kmdf-ver:
req.umdf-ver:
req.lib:
req.dll:
req.ddi-compliance:
req.unicode-ansi:
req.max-support:
req.typenames: D3D12DDI_GPU_VIRTUAL_ADDRESS_AND_STRIDE
topic_type: 
- apiref
api_type: 
- HeaderDef
api_location: 
- d3d12umddi.h
api_name: 
- D3D12DDI_GPU_VIRTUAL_ADDRESS_AND_STRIDE
product:
- Windows
targetos: Windows
tech.root: display
dev_langs:
 - c++
ms.custom: RS5
---

# D3D12DDI_GPU_VIRTUAL_ADDRESS_AND_STRIDE structure

## -description

Describes the GPU virtual address and stride.

## -struct-fields

### -field StartAddress

The beginning of a virtual address range.

### -field StrideInBytes
 
Defines the indexing stride in bytes, such as for vertices. Only the bottom 32 bits get used. The field is 64 bits purely to make alignment of containing structures clean and obvious everywhere.

## -remarks

## -see-also
