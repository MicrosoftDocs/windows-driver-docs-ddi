---
UID: NE:d3d12umddi.D3D12DDI_DISPATCH_MODE_0108
tech.root: display
title: D3D12DDI_DISPATCH_MODE_0108
ms.date: 05/03/2024
targetos: Windows
description: Learn more about the D3D12DDI_DISPATCH_MODE_0108 enumeration.
prerelease: false
req.construct-type: enumeration
req.ddi-compliance: 
req.header: d3d12umddi.h
req.include-header: 
req.kmdf-ver: 
req.max-support: 
req.target-min-winverclnt: Windows 11, version 24H2 (WDDM 3.2)
req.target-min-winversvr: 
req.target-type: 
req.typenames: 
typedef_isUnnamed: false
req.umdf-ver: 
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - d3d12umddi.h
api_name:
 - D3D12DDI_DISPATCH_MODE_0108
f1_keywords:
 - D3D12DDI_DISPATCH_MODE_0108
 - d3d12umddi/D3D12DDI_DISPATCH_MODE_0108
dev_langs:
 - c++
helpviewer_keywords:
 - D3D12DDI_DISPATCH_MODE_0108
---

# D3D12DDI_DISPATCH_MODE_0108 enumeration (d3d12umddi.h)

## -description

The **D3D12DDI_DISPATCH_MODE_0108** enumeration identifies a work graph's dispatch mode and which union member in [**D3D12DDI_DISPATCH_GRAPH_DESC_0108**](ns-d3d12umddi-d3d12ddi_dispatch_graph_desc_0108.md) to use.

## -enum-fields

### -field D3D12DDI_DISPATCH_MODE_NODE_CPU_INPUT_0108

The dispatch is a single node configured from the CPU. Use the **NodeCPUInput** union member.

### -field D3D12DDI_DISPATCH_MODE_NODE_GPU_INPUT_0108

The dispatch is a single node configured from the GPU. Use the **NodeGPUInput** union member.

### -field D3D12DDI_DISPATCH_MODE_MULTI_NODE_CPU_INPUT_0108

The dispatch is a multi-node configured from the CPU. Use the **MultiNodeCPUInput** union member.

### -field D3D12DDI_DISPATCH_MODE_MULTI_NODE_GPU_INPUT_0108

The dispatch is a multi-node configured from the GPU. Use the **MultiNodeGPUInput** union member.

## -remarks

For more information, see [Work graphs](/windows-hardware/drivers/display/work-graphs).

## -see-also

[**D3D12DDI_DISPATCH_GRAPH_DESC_0108**](ns-d3d12umddi-d3d12ddi_dispatch_graph_desc_0108.md)

[**PFND3D12DDI_DISPATCH_GRAPH_0108**](nc-d3d12umddi-pfnd3d12ddi_dispatch_graph_0108.md)
