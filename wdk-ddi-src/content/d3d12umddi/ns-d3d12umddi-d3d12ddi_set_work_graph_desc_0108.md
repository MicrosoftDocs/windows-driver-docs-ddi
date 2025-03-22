---
UID: NS:d3d12umddi.D3D12DDI_SET_WORK_GRAPH_DESC_0108
tech.root: display
title: D3D12DDI_SET_WORK_GRAPH_DESC_0108
ms.date: 05/03/2024
targetos: Windows
description: Learn more about the D3D12DDI_SET_WORK_GRAPH_DESC_0108 structure.
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
req.typenames: D3D12DDI_SET_WORK_GRAPH_DESC_0108
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
 - D3D12DDI_SET_WORK_GRAPH_DESC_0108
f1_keywords:
 - D3D12DDI_SET_WORK_GRAPH_DESC_0108
 - d3d12umddi/D3D12DDI_SET_WORK_GRAPH_DESC_0108
dev_langs:
 - c++
helpviewer_keywords:
 - D3D12DDI_SET_WORK_GRAPH_DESC_0108
---

# D3D12DDI_SET_WORK_GRAPH_DESC_0108 structure (d3d12umddi.h)

## -description

A **D3D12DDI_SET_WORK_GRAPH_DESC_0108** structure describes a work graph to set when the **Type** field of a [**D3D12DDI_SET_PROGRAM_DESC_0108**](ns-d3d12umddi-d3d12ddi_set_program_desc_0108.md) structure is **D3D12DDI_PROGRAM_TYPE_WORK_GRAPH_0108**.

## -struct-fields

### -field ProgramIdentifier

A [**D3D12DDI_PROGRAM_IDENTIFIER_0108**](ns-d3d12umddi-d3d12ddi_program_identifier_0108.md) structure that identifies the program to set.

### -field Flags

A [**D3D12DDI_SET_WORK_GRAPH_FLAGS_0108**](ne-d3d12umddi-d3d12ddi_set_work_graph_flags_0108.md) enumeration that specifies flags for setting the work graph.

### -field BackingMemory

A [**D3D12DDI_GPU_VIRTUAL_ADDRESS_RANGE**](ns-d3d12umddi-d3d12ddi_gpu_virtual_address_range.md) structure that specifies the backing memory for the work graph. The address must be 8-byte aligned.

### -field NodeLocalRootArgumentsTable

A [**D3D12DDI_GPU_VIRTUAL_ADDRESS_RANGE_AND_STRIDE**](ns-d3d12umddi-d3d12ddi_gpu_virtual_address_range_and_stride.md) structure that specifies the location of the local root arguments table. See the members of [**D3D12DDI_SHADER_NODE_0108**](ns-d3d12umddi-d3d12ddi_shader_node_0108.md) in a work graph definition at the DDI indicating what the local root argument table index for a given node in a work graph is, if any.

## -remarks

For more information, see [Work graphs](/windows-hardware/drivers/display/work-graphs).

## -see-also

[**D3D12DDI_SET_PROGRAM_DESC_0108**](ns-d3d12umddi-d3d12ddi_set_program_desc_0108.md)  

[**PFND3D12DDI_SET_PROGRAM_0108**](nc-d3d12umddi-pfnd3d12ddi_set_program_0108.md)
