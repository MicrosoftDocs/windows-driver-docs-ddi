---
UID: NS:d3d12umddi.D3D12DDI_MULTI_NODE_CPU_INPUT_0108
tech.root: display
title: D3D12DDI_MULTI_NODE_CPU_INPUT_0108
ms.date: 05/03/2024
targetos: Windows
description: Learn more about the D3D12DDI_MULTI_NODE_CPU_INPUT_0108 structure.
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
req.target-min-winverclnt: Windows 11, version 24H2 (WDDM 3.2) 
req.target-min-winversvr: 
req.target-type: 
req.typenames: D3D12DDI_MULTI_NODE_CPU_INPUT_0108
typedef_isUnnamed: false
req.umdf-ver: 
req.unicode-ansi: 
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - d3d12umddi.h
api_name:
 - D3D12DDI_MULTI_NODE_CPU_INPUT_0108
f1_keywords:
 - D3D12DDI_MULTI_NODE_CPU_INPUT_0108
 - d3d12umddi/D3D12DDI_MULTI_NODE_CPU_INPUT_0108
dev_langs:
 - c++
helpviewer_keywords:
 - D3D12DDI_MULTI_NODE_CPU_INPUT_0108
---

# D3D12DDI_MULTI_NODE_CPU_INPUT_0108 structure (d3d12umddi.h)

## -description

The **D3D12DDI_MULTI_NODE_CPU_INPUT_0108** structure describes the input data for multiple nodes within a work graph where the input is provided by the CPU.

## -struct-fields

### -field NumNodeInputs

The number of entries in the array that **pNodeInputs** points to.

### -field pNodeInputs

Pointer to an array of [**D3D12DDI_NODE_CPU_INPUT_0108**](ns-d3d12umddi-d3d12ddi_node_cpu_input_0108.md) structures.

### -field NodeInputStrideInBytes

Distance between each **D3D12DDI_NODE_CPU_INPUT_0108** structure in the array that **pNodeInputs** points to, in bytes.

## -remarks

For more information, see [Work graphs](/windows-hardware/drivers/display/work-graphs).

## -see-also

[**D3D12DDI_DISPATCH_GRAPH_DESC_0108**](ns-d3d12umddi-d3d12ddi_dispatch_graph_desc_0108.md)

[**PFND3D12DDI_DISPATCH_GRAPH_0108**](nc-d3d12umddi-pfnd3d12ddi_dispatch_graph_0108.md)
