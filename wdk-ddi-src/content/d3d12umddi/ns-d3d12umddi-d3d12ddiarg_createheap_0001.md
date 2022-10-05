---
UID: NS:d3d12umddi.D3D12DDIARG_CREATEHEAP_0001
tech.root: display
title: D3D12DDIARG_CREATEHEAP_0001
ms.date: 09/22/2022
targetos: Windows
description: Learn more about the D3D12DDIARG_CREATEHEAP_0001 structure.
prerelease: false
req.construct-type: structure
req.ddi-compliance: 
req.dll: 
req.header: d3d12umddi.h
req.include-header: 
req.kmdf-ver: 
req.lib: 
req.max-support: 
req.redist: 
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.target-type: 
req.typenames: D3D12DDIARG_CREATEHEAP_0001
req.umdf-ver: 
req.unicode-ansi: 
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - d3d12umddi.h
api_name:
 - D3D12DDIARG_CREATEHEAP_0001
f1_keywords:
 - D3D12DDIARG_CREATEHEAP_0001
 - d3d12umddi/D3D12DDIARG_CREATEHEAP_0001
dev_langs:
 - c++
helpviewer_keywords:
 - D3D12DDIARG_CREATEHEAP_0001
---

## -description

The **D3D12DDIARG_CREATEHEAP_0001** structure describes a heap.

## -struct-fields

### -field ByteSize

Size of the heap, in bytes.

### -field Alignment

The alignment value of the heap. See [**D3D12_HEAP_DESC**](/windows/win32/api/d3d12/ns-d3d12-d3d12_heap_desc) for a list of possible values.

### -field MemoryPool

A [**D3D12DDI_MEMORY_POOL**](ne-d3d12umddi-d3d12ddi_memory_pool.md) value that specifies the memory pool for the heap.

### -field CPUPageProperty

A [**D3D12DDI_CPU_PAGE_PROPERTY**](ne-d3d12umddi-d3d12ddi_cpu_page_property.md) value that specifies the CPU page properties for the heap.

### -field Flags

A [**D3D12DDI_HEAP_FLAGS**](ne-d3d12umddi-d3d12ddi_heap_flags.md) value with a bit-wise OR of heap options.

### -field CreationNodeMask

For multi-adapter operations, this indicates the node where the resource should be created.

Exactly one bit of this UINT must be set. See [Multi-adapter systems](/windows/win32/direct3d12/multi-engine).

Passing zero is equivalent to passing one, in order to simplify the usage of single-GPU adapters.

### -field VisibleNodeMask

For multi-adapter operations, this indicates the set of nodes where the resource is visible.

**VisibleNodeMask** must have the same bit set that is set in **CreationNodeMask**. **VisibleNodeMask** can also have additional bits set for cross-node resources, but doing so can potentially reduce performance for resource accesses, so you should do so only when needed.

Passing zero is equivalent to passing one, in order to simplify the usage of single-GPU adapters.

## -remarks

## -see-also

