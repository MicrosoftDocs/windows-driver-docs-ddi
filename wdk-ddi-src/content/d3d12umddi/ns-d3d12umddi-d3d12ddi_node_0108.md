---
UID: NS:d3d12umddi._D3D12DDI_NODE_0108
tech.root: display
title: D3D12DDI_NODE_0108
ms.date: 05/03/2024
targetos: Windows
description: Learn more about the _D3D12DDI_NODE_0108 structure.
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
req.typenames: D3D12DDI_NODE_0108
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
 - _D3D12DDI_NODE_0108
 - D3D12DDI_NODE_0108
f1_keywords:
 - _D3D12DDI_NODE_0108
 - d3d12umddi/_D3D12DDI_NODE_0108
 - D3D12DDI_NODE_0108
 - d3d12umddi/D3D12DDI_NODE_0108
dev_langs:
 - c++
helpviewer_keywords:
 - _D3D12DDI_NODE_0108
---

# D3D12DDI_NODE_0108 structure (d3d12umddi.h)

## -description

The **D3D12DDI_NODE_0108** structure describes a node in a work graph.

## -struct-fields

### -field VersionAdded

Version number that the node was added to the state object, starting at 0 for the initial work graph. This value only becomes relevant when [**PFND3D12DDI_ADD_TO_STATE_OBJECT_0072**](nc-d3d12umddi-pfnd3d12ddi_add_to_state_object_0072.md) starts being used to add nodes to a work graph, in which case the version number distingushes when the node was added. The structure of a graph at any given version can be identified by considering any version less or equal to the relevant version number.

### -field NodeType

A [**D3D12DDI_NODE_TYPE_0108**](ne-d3d12umddi-d3d12ddi_node_type_0108.md) enumeration that specifies the type of the node and which union member is valid.

### -field Shader

A [**D3D12DDI_SHADER_NODE_0108**](ns-d3d12umddi-d3d12ddi_shader_node_0108.md) structure that describes a shader node.

## -remarks

Pointers to this structure at the DDI level (for example, from other node descriptions) are stable, which is of particular importance across [**PFND3D12DDI_ADD_TO_STATE_OBJECT_0072**](nc-d3d12umddi-pfnd3d12ddi_add_to_state_object_0072.md) additions.

For more information, see [Work graphs](/windows-hardware/drivers/display/work-graphs).

## -see-also

[**D3D12DDI_NODE_LIST_ENTRY_0108**](ns-d3d12umddi-d3d12ddi_node_list_entry_0108.md)

[**D3D12DDI_WORK_GRAPH_DESC_0108**](ns-d3d12umddi-d3d12ddi_work_graph_desc_0108.md)

[**PFND3D12DDI_ADD_TO_STATE_OBJECT_0072**](nc-d3d12umddi-pfnd3d12ddi_add_to_state_object_0072.md)

[**PFND3D12DDI_CREATE_STATE_OBJECT_0054**](nc-d3d12umddi-pfnd3d12ddi_create_state_object_0054.md)

[**PFND3D12DDI_DISPATCH_GRAPH_0108**](nc-d3d12umddi-pfnd3d12ddi_dispatch_graph_0108.md)
