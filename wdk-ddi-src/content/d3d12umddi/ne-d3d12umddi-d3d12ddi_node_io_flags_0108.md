---
UID: NE:d3d12umddi.D3D12DDI_NODE_IO_FLAGS_0108
tech.root: display
title: D3D12DDI_NODE_IO_FLAGS_0108
ms.date: 05/03/2024
targetos: Windows
description: Learn more about the D3D12DDI_NODE_IO_FLAGS_0108 enumeration.
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
 - D3D12DDI_NODE_IO_FLAGS_0108
f1_keywords:
 - D3D12DDI_NODE_IO_FLAGS_0108
 - d3d12umddi/D3D12DDI_NODE_IO_FLAGS_0108
dev_langs:
 - c++
helpviewer_keywords:
 - D3D12DDI_NODE_IO_FLAGS_0108
---

# D3D12DDI_NODE_IO_FLAGS_0108 enumeration (d3d12umddi.h)

## -description

The **D3D12DDI_NODE_IO_FLAGS_0108** enumeration specifies flags used to describe the I/O behavior of a node in a work graph.

## -enum-fields

### -field D3D12DDI_NODE_IO_FLAG_INPUT

The node is designed to receive input data.

### -field D3D12DDI_NODE_IO_FLAG_OUTPUT

The node produces output data.

### -field D3D12DDI_NODE_IO_FLAG_READ_WRITE

The node can be read from and written to.

### -field D3D12DDI_NODE_IO_FLAG_EMPTY_RECORD

The node has an empty record.

### -field D3D12DDI_NODE_IO_FLAG_NODE_ARRAY

The node is a part of an array of nodes.

### -field D3D12DDI_NODE_IO_FLAG_THREAD_RECORD

The node is a thread record.

### -field D3D12DDI_NODE_IO_FLAG_GROUP_RECORD

The node is a group record.

### -field D3D12DDI_NODE_IO_FLAG_DISPATCH_RECORD

The node is a dispatch record.

### -field D3D12DDI_NODE_IO_FLAG_RECORD_GRANULARITY_MASK

A mask that can be used to extract the record granularity from the flags.

### -field D3D12DDI_NODE_IO_FLAG_KIND_MASK

A mask that can be used to extract the node's I/O kind from the flags.

### -field D3D12DDI_NODE_IO_FLAG_TRACK_RW_INPUT_SHARING

The node tracks read-write input sharing.

### -field D3D12DDI_NODE_IO_FLAG_NODE_FLAGS_MASK

A mask for extracting node-specific flags.

### -field D3D12DDI_NODE_IO_FLAG_RECORD_FLAGS_MASK

A mask for extracting flags related to the node's record behavior.

## -remarks

These flags are a DDI copy of the flags in [NodeIOFlags and NodeIOKind encoding](https://github.com/microsoft/DirectX-Specs/blob/master/d3d/WorkGraphs.md#nodeioflags-and-nodeiokind-encoding) in DXIL metadata.

For more information, see [Work graphs](/windows-hardware/drivers/display/work-graphs).

## -see-also

[**D3D12DDI_NODE_IO_KIND_0108**](ne-d3d12umddi-d3d12ddi_node_io_kind_0108.md)