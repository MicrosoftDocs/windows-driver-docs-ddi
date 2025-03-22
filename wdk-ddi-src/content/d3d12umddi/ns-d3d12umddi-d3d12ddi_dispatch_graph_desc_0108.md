---
UID: NS:d3d12umddi.D3D12DDI_DISPATCH_GRAPH_DESC_0108
tech.root: display
title: D3D12DDI_DISPATCH_GRAPH_DESC_0108
ms.date: 05/03/2024
targetos: Windows
description: Learn more about the D3D12DDI_DISPATCH_GRAPH_DESC_0108 structure.
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
req.typenames: D3D12DDI_DISPATCH_GRAPH_DESC_0108
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
 - D3D12DDI_DISPATCH_GRAPH_DESC_0108
f1_keywords:
 - D3D12DDI_DISPATCH_GRAPH_DESC_0108
 - d3d12umddi/D3D12DDI_DISPATCH_GRAPH_DESC_0108
dev_langs:
 - c++
helpviewer_keywords:
 - D3D12DDI_DISPATCH_GRAPH_DESC_0108
---

# D3D12DDI_DISPATCH_GRAPH_DESC_0108 structure (d3d12umddi.h)

## -description

The **D3D12DDI_DISPATCH_GRAPH_DESC_0108** structure is the input parameter for [**PFND3D12DDI_DISPATCH_GRAPH_0108**](nc-d3d12umddi-pfnd3d12ddi_dispatch_graph_0108.md). It describes the work graph to dispatch.

## -struct-fields

### -field Mode

A [**D3D12DDI_DISPATCH_MODE_0108**](ne-d3d12umddi-d3d12ddi_dispatch_mode_0108.md) enumeration that specifies the work graph's mode and which entry in the union to use.

### -field NodeCPUInput

The [**D3D12DDI_NODE_CPU_INPUT_0108**](ns-d3d12umddi-d3d12ddi_node_cpu_input_0108.md) structure to use when **Mode** is **D3D12DDI_DISPATCH_MODE_NODE_CPU_INPUT_0108**.

### -field NodeGPUInput

A **D3D12DDI_GPU_VIRTUAL_ADDRESS** to use when **Mode** is **D3D12DDI_DISPATCH_MODE_NODE_GPU_INPUT_0108**.

### -field MultiNodeCPUInput

A [**D3D12DDI_MULTI_NODE_CPU_INPUT_0108**](ns-d3d12umddi-d3d12ddi_multi_node_cpu_input_0108.md) structure to use when **Mode** is **D3D12DDI_DISPATCH_MODE_MULTI_NODE_CPU_INPUT_0108**.

### -field MultiNodeGPUInput

A **D3D12DDI_GPU_VIRTUAL_ADDRESS** to use when **Mode** is **D3D12DDI_DISPATCH_MODE_MULTI_NODE_GPU_INPUT_0108**.

## -remarks

For more information, see [Work graphs](/windows-hardware/drivers/display/work-graphs).

## -see-also

[**D3D12DDI_DISPATCH_MODE_0108**](ne-d3d12umddi-d3d12ddi_dispatch_mode_0108.md)

[**PFND3D12DDI_DISPATCH_GRAPH_0108**](nc-d3d12umddi-pfnd3d12ddi_dispatch_graph_0108.md)
