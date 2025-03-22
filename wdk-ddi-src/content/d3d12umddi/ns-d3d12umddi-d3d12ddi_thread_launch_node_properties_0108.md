---
UID: NS:d3d12umddi.D3D12DDI_THREAD_LAUNCH_NODE_PROPERTIES_0108
tech.root: display
title: D3D12DDI_THREAD_LAUNCH_NODE_PROPERTIES_0108
ms.date: 05/03/2024
targetos: Windows
description: Learn more about the D3D12DDI_THREAD_LAUNCH_NODE_PROPERTIES_0108 structure.
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
req.typenames: D3D12DDI_THREAD_LAUNCH_NODE_PROPERTIES_0108
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
 - D3D12DDI_THREAD_LAUNCH_NODE_PROPERTIES_0108
f1_keywords:
 - D3D12DDI_THREAD_LAUNCH_NODE_PROPERTIES_0108
 - d3d12umddi/D3D12DDI_THREAD_LAUNCH_NODE_PROPERTIES_0108
dev_langs:
 - c++
helpviewer_keywords:
 - D3D12DDI_THREAD_LAUNCH_NODE_PROPERTIES_0108
---

# D3D12DDI_THREAD_LAUNCH_NODE_PROPERTIES_0108 structure (d3d12umddi.h)

## -description

The **D3D12DDI_THREAD_LAUNCH_NODE_PROPERTIES_0108** structure describes the properties of a thread launch node.

## -struct-fields

### -field FinalName

A [**D3D12DDI_NODE_ID_0108**](ns-d3d12umddi-d3d12ddi_node_id_0108.md) structure that specifies the final name of the node after any optional renames done at the application level.

### -field bProgramEntry

When TRUE, the current node is a program entry and is listed in the **pEntrypoints** list in [**D3D12DDI_WORK_GRAPH_DESC_0108**](ns-d3d12umddi-d3d12ddi_work_graph_desc_0108.md). As such this parameter is redundant, but it's present for clarity. The shader might not have declared that the node is an entrypoint but the runtime might have determined it must be one, or at the API the choice might have been overridden in some way. This member is always TRUE for a node that isn't targeted by any other nodes in the graph.

### -field InputNodeIOKind

A [**D3D12DDI_NODE_IO_KIND_0108**](ne-d3d12umddi-d3d12ddi_node_io_kind_0108.md) enumeration that specifies the class of input. See [Node input declaration](https://github.com/microsoft/DirectX-Specs/blob/master/d3d/WorkGraphs.md#node-input-declaration).

### -field InputNodeIOFlags

Flags that provide additional information about the node's input I/O. See the flags within **D3D12DDI_NODE_IO_FLAGS_FLAG_MASK** in [**D3D12DDI_NODE_IO_FLAGS_0108**](ne-d3d12umddi-d3d12ddi_node_io_flags_0108.md). For an input, the only flag that applies is **D3D12DDI_NODE_IO_FLAG_TRACK_RW_INPUT_SHARING**.

### -field InputRecordSizeInBytes

Size of the input record, in bytes. Can be 0 if **InputNodeIOKind** is **D3D12DDI_NODE_IO_KIND_EMPTY_INPUT_0108**.

### -field GroupSharedUsageInBytes

Size of group shared usage by the node, in bytes.

### -field MaxRecursionDepth

Max recursion declared by shader. A value of 0 means no recursion.

### -field pLocalRootArgumentsTableIndex

If a local root signature has been associated with the shader and/or the shader explicitly declared a local root argument table index it wants to use, the 0-based index is pointed to here. The runtime may have auto-assigned a location. If no local root signature has been associated with the shader, this will be ```nullptr```.

### -field pShareInputOfNode

Optional pointer to a node that shares the same input with this node, or ```nullptr``` if the current node isn't sharing another node's input. If this node is sharing its input from another node in the work graph, **pShareInputOfNode** points to that node, represented by a [**D3D12DDI_NODE_0108**](ns-d3d12umddi-d3d12ddi_node_0108.md) structure. If multiple nodes are in an input sharing set, all but the source node point to the source node, and the source node instead sets the **pNodesSharingInputWithThisNode** parameter to point to the others.

### -field pInputNodes

Pointer to a list ([**D3D12DDI_NODE_LIST_ENTRY_0108**](ns-d3d12umddi-d3d12ddi_node_list_entry_0108.md)) of nodes ([**(D3D12DDI_NODE_0108**](ns-d3d12umddi-d3d12ddi_node_0108.md)) that target the current node. **pInputNodes** is ```nullptr``` if no nodes target this node.

### -field pNodesSharingInputWithThisNode

Pointer to a list ([**D3D12DDI_NODE_LIST_ENTRY_0108**](ns-d3d12umddi-d3d12ddi_node_list_entry_0108.md)) of nodes ([**(D3D12DDI_NODE_0108**](ns-d3d12umddi-d3d12ddi_node_0108.md)) that share input with the current node. **pNodesSharingInputWithThisNode** is ```nullptr``` if no nodes share input with this node.

### -field NumOutputs

Number of nodes that this node outputs to.

### -field pOutputs

Pointer to an array of **NumOutputs** [**D3D12DDI_NODE_OUTPUT_0108**](ns-d3d12umddi-d3d12ddi_node_output_0108.md) structures that contain output definitions. **pOutputs** is ```nullptr``` if this node doesn't output to other nodes.

## -remarks

Any properties listed here take precedence over (override) what might have been declared in the shader for the node. The driver must always use the properties listed here as the final property selections. If a driver happens to care about whether something was overridden, it can compare any setting here against what the shader declared.

For more information, see [Work graphs](/windows-hardware/drivers/display/work-graphs).

## -see-also

[**D3D12DDI_SHADER_NODE_0108**](ns-d3d12umddi-d3d12ddi_shader_node_0108.md)
