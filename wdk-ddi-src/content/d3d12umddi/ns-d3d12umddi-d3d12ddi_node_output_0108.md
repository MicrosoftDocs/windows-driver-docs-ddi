---
UID: NS:d3d12umddi.D3D12DDI_NODE_OUTPUT_0108
tech.root: display
title: D3D12DDI_NODE_OUTPUT_0108
ms.date: 05/03/2024
targetos: Windows
description: Learn more about the D3D12DDI_NODE_OUTPUT_0108 structure.
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
req.typenames: D3D12DDI_NODE_OUTPUT_0108
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
 - D3D12DDI_NODE_OUTPUT_0108
f1_keywords:
 - D3D12DDI_NODE_OUTPUT_0108
 - d3d12umddi/D3D12DDI_NODE_OUTPUT_0108
dev_langs:
 - c++
helpviewer_keywords:
 - D3D12DDI_NODE_OUTPUT_0108
---

# D3D12DDI_NODE_OUTPUT_0108 structure (d3d12umddi.h)

## -description

The **D3D12DDI_NODE_OUTPUT_0108** structure describes the output of a node in a work graph.

## -struct-fields

### -field FinalName

A [**D3D12DDI_NODE_ID_0108**](ns-d3d12umddi-d3d12ddi_node_id_0108.md) structure that specifies the final name of the node after any optional renames done at the application level. If **ArraySize** is greater than 1, this is the NodeID of beginning of the array of nodes being output to.

### -field OutputIndex

Zero-based index of this output in the set of outputs for this node (node array output counts as one entry in this set). This index matches the order the outputs are declared, and how they appear in the **pOutputs** arrays in [**D3D12DDI_BROADCASTING_LAUNCH_NODE_PROPERTIES_0108**](ns-d3d12umddi-d3d12ddi_broadcasting_launch_node_properties_0108.md), [**D3D12DDI_COALESCING_LAUNCH_NODE_PROPERTIES_0108**](ns-d3d12umddi-d3d12ddi_coalescing_launch_node_properties_0108.md), and [**D3D12DDI_THREAD_LAUNCH_NODE_PROPERTIES_0108**](ns-d3d12umddi-d3d12ddi_thread_launch_node_properties_0108.md). As such, this value is redundant, but provided for clarity. Other members of this structure reference nodes using this indexing space.

### -field NodeIOKind

A [**D3D12DDI_NODE_IO_KIND_0108**](ne-d3d12umddi-d3d12ddi_node_io_kind_0108.md) enumeration that specifies the class of input. See [Node output declaration](https://github.com/microsoft/DirectX-Specs/blob/master/d3d/WorkGraphs.md#node-output-declaration).

### -field NodeIOFlags

Flags that provide additional information about the node's output. See the flags within **D3D12DDI_NODE_IO_FLAGS_FLAG_MASK** in [**D3D12DDI_NODE_IO_FLAGS_0108**](ne-d3d12umddi-d3d12ddi_node_io_flags_0108.md). See also [Node input declaration](https://github.com/microsoft/DirectX-Specs/blob/master/d3d/WorkGraphs.md#node-input-declaration).

### -field RecordSizeInBytes

Size of the output record, in bytes. Can be 0 if **NodeIOKind** is **D3D12DDI_NODE_IO_KIND_EMPTY_OUTPUT_0108**.

### -field bAllowSparseNodes

Boolean that specifies whether sparse nodes are allowed. This member maps to the [AllowSparseNodes attribute](https://github.com/microsoft/DirectX-Specs/blob/master/d3d/WorkGraphs.md#node-output-attributes) on a node output, or can be overridden at the application level, so the final status is indicated here.

### -field pRecordDispatchGrid

If ```nullptr```, the output record doesn't contain [*SV_DispatchGrid*](https://github.com/microsoft/DirectX-Specs/blob/master/d3d/WorkGraphs.md#sv_dispatchgrid). Else, points to a description of how *SV_DispatchGrid* appears in the output record. See [**D3D12DDI_RECORD_DISPATCH_GRID_0108**](ns-d3d12umddi-d3d12ddi_record_dispatch_grid_0108.md).

### -field pMaxRecords

Maximum number of output records that a thread group will output to this output node/array. If the output record budget for this output is shared with another output, **pMaxRecords** is ```nullptr``` and **pMaxRecordsSharedWithOutputIndex** is specified instead. If the shader declared [[MaxRecordsSharedWith()]](https://github.com/microsoft/DirectX-Specs/blob/master/d3d/WorkGraphs.md#sv_dispatchgrid), it's valid to override it with **pMaxRecords**, which makes the output budget no longer shared.

### -field pMaxRecordsSharedWithOutputIndex

If this output shares its output record budget with another output, **pMaxRecordsSharedWithOutputIndex** points to the 0-based index of that output based on the order they are declared, and how they appear in the **pOutputs** arrays in  [**D3D12DDI_BROADCASTING_LAUNCH_NODE_PROPERTIES_0108**](ns-d3d12umddi-d3d12ddi_broadcasting_launch_node_properties_0108.md), [**D3D12DDI_COALESCING_LAUNCH_NODE_PROPERTIES_0108**](ns-d3d12umddi-d3d12ddi_coalescing_launch_node_properties_0108.md), and [**D3D12DDI_THREAD_LAUNCH_NODE_PROPERTIES_0108**](ns-d3d12umddi-d3d12ddi_thread_launch_node_properties_0108.md). The output that is pointed to has **pMaxRecords** specified. If the current output doesn't share its output record budget, **pMaxRecordsSharedWithIndex** is ```nullptr```. If the shader declared [MaxRecords()], it is valid to override it with **pMaxRecordsSharedWithIndex**, which makes the output budget now shared with another output.

### -field ArraySize

The number of nodes in the array of nodes being output to. If this is 1, the output is a single node. If this is greater than 1, the output is an array of nodes. The nodes are contiguous in the array, and the first node is the one specified by **FinalName**. A value of ```0xffffffff``` means unbounded node array size, which is only permitted when **bAllowSparseNodes** is true.

### -field pOutputs

List ([**D3D12DDI_NODE_LIST_ENTRY**](ns-d3d12umddi-d3d12ddi_node_list_entry_0108.md)) of nodes ([**D3D12DDI_NODE_0108**](ns-d3d12umddi-d3d12ddi_node_0108.md)) that this node outputs to. If **pOutputs** is ```nullptr``` this node doesn't output to other nodes. If **bAllowSparseNodes** is true, this list isn't necessarily as long as **ArraySize**. Regardless of **bAllowSparseNodes** state, drivers shouldn't assume the list entries is in array index order. The array index of a given output can be found in its node ID. When [AddToStateObject()](https://github.com/microsoft/DirectX-Specs/blob/master/d3d/WorkGraphs.md#addtostateobject) adds outputs, additions will appear at the start of the list, which is another reason not to assume they are array index order.

## -remarks

For more information, see [Work graphs](/windows-hardware/drivers/display/work-graphs).

## -see-also

[**D3D12DDI_BROADCASTING_LAUNCH_NODE_PROPERTIES_0108**](ns-d3d12umddi-d3d12ddi_broadcasting_launch_node_properties_0108.md)

[**D3D12DDI_COALESCING_LAUNCH_NODE_PROPERTIES_0108**](ns-d3d12umddi-d3d12ddi_coalescing_launch_node_properties_0108.md)

[**D3D12DDI_THREAD_LAUNCH_NODE_PROPERTIES_0108**](ns-d3d12umddi-d3d12ddi_thread_launch_node_properties_0108.md)  
