---
UID: NE:d3d12umddi.D3D12DDI_NODE_IO_KIND_0108
tech.root: display
title: D3D12DDI_NODE_IO_KIND_0108
ms.date: 05/03/2024
targetos: Windows
description: Learn more about the D3D12DDI_NODE_IO_KIND_0108 enumeration.
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
 - D3D12DDI_NODE_IO_KIND_0108
f1_keywords:
 - D3D12DDI_NODE_IO_KIND_0108
 - d3d12umddi/D3D12DDI_NODE_IO_KIND_0108
dev_langs:
 - c++
helpviewer_keywords:
 - D3D12DDI_NODE_IO_KIND_0108
---

# D3D12DDI_NODE_IO_KIND_0108 enumeration (d3d12umddi.h)

## -description

The **D3D12DDI_NODE_IO_KIND_0108** enumeration specifies the class of input or output for a node in a work graph.

## -enum-fields

### -field D3D12DDI_NODE_IO_KIND_INVALID

The node I/O is invalid or uninitialized.

### -field D3D12DDI_NODE_IO_KIND_EMPTY_INPUT_0108

The node has an empty input.

### -field D3D12DDI_NODE_IO_KIND_NODE_OUTPUT_0108

The node produces an output that may be read from and written to.

### -field D3D12DDI_NODE_IO_KIND_NODE_OUTPUT_ARRAY_0108

Signifies an array of node outputs with read-write capabilities.

### -field D3D12DDI_NODE_IO_KIND_EMPTY_OUTPUT_0108

The node has an empty output (no data is produced).

### -field D3D12DDI_NODE_IO_KIND_EMPTY_OUTPUT_ARRAY_0108

Signifies an array of nodes with empty outputs.

### -field D3D12DDI_NODE_IO_KIND_DISPATCH_NODE_INPUT_RECORD_0108

Signifies a dispatch node input record.

### -field D3D12DDI_NODE_IO_KIND_GROUP_NODE_INPUT_RECORDS_0108

Signifies group node input records.

### -field D3D12DDI_NODE_IO_KIND_THREAD_NODE_INPUT_RECORD_0108

Signifies a thread node input record.

### -field D3D12DDI_NODE_IO_KIND_READ_WRITE_DISPATCH_NODE_INPUT_RECORD_0108

Signifies a read-write dispatch node input record.

### -field D3D12DDI_NODE_IO_KIND_READ_WRITE_GROUP_NODE_INPUT_RECORDS_0108

Signifies read-write group node input records.

### -field D3D12DDI_NODE_IO_KIND_READ_WRITE_THREAD_NODE_INPUT_RECORD_0108

Signifies a read-write thread node input record.

### -field D3D12DDI_NODE_IO_KIND_GROUP_NODE_OUTPUT_RECORDS_0108

Signifies group node output records.

### -field D3D12DDI_NODE_IO_KIND_THREAD_NODE_OUTPUT_RECORDS_0108

Signifies thread node output records.

## -remarks

Each enum definition is comprised of a set of [**D3D12DDI_NODE_IO_FLAGS_0108**](ne-d3d12umddi-d3d12ddi_node_io_flags_0108.md) flags, within **D3D12DDI_NODE_IO_FLAG_KIND_MASK**. This enum is a DDI copy of the NodeIOKind portion of the [NodeIOFlags and NodeIOKind encoding](https://github.com/microsoft/DirectX-Specs/blob/master/d3d/WorkGraphs.md#nodeioflags-and-nodeiokind-encoding) in DXIL metadata.

## -see-also

[**D3D12DDI_BROADCASTING_LAUNCH_NODE_PROPERTIES_0108**](ns-d3d12umddi-d3d12ddi_broadcasting_launch_node_properties_0108.md)

[**D3D12DDI_COALESCING_LAUNCH_NODE_PROPERTIES_0108**](ns-d3d12umddi-d3d12ddi_coalescing_launch_node_properties_0108.md)

[**D3D12DDI_NODE_OUTPUT_0108**](ns-d3d12umddi-d3d12ddi_node_output_0108.md)

[**D3D12DDI_THREAD_LAUNCH_NODE_PROPERTIES_0108**](ns-d3d12umddi-d3d12ddi_thread_launch_node_properties_0108.md)

[**D3D12DDI_SHADER_NODE_0108**](ns-d3d12umddi-d3d12ddi_shader_node_0108.md)
