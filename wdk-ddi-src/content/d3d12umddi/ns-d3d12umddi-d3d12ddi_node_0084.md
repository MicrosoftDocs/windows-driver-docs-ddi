---
UID: NS:d3d12umddi.D3D12DDI_NODE_0084
tech.root: display
title: D3D12DDI_NODE_0084
ms.date: 09/09/2024
targetos: Windows
description: Learn more about the D3D12DDI_NODE_0084 structure.
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
req.typenames: D3D12DDI_NODE_0084
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
 - D3D12DDI_NODE_0084
f1_keywords:
 - D3D12DDI_NODE_0084
 - d3d12umddi/D3D12DDI_NODE_0084
dev_langs:
 - c++
helpviewer_keywords:
 - D3D12DDI_NODE_0084
---

## -description

The **D3D12DDI_NODE_0084** structure describes a node in a work graph.

## -struct-fields

### -field NodeIndex

The index of the node in the work graph.

### -field NodeType

A [**D3D12DDI_NODE_TYPE_0084**](ne-d3d12umddi-d3d12ddi_node_type_0084.md) enumeration that specifies the type of the node and which union member is valid.

### -field Shader

A [**D3D12DDI_SHADER_NODE_0084**](ns-d3d12umddi-d3d12ddi_shader_node_0084.md) structure that describes the shader node.

## -remarks

For more information, see [Work graphs](/windows-hardware/drivers/display/work-graphs).

## -see-also

[**D3D12DDI_WORK_GRAPH_DESC_0084**](ns-d3d12umddi-d3d12ddi_work_graph_desc_0084.md)

[**PFND3D12DDI_ADD_TO_STATE_OBJECT_0072**](nc-d3d12umddi-pfnd3d12ddi_add_to_state_object_0072.md)

[**PFND3D12DDI_CREATE_STATE_OBJECT_0054**](nc-d3d12umddi-pfnd3d12ddi_create_state_object_0054.md)

[**PFND3D12DDI_DISPATCH_GRAPH_0084**](nc-d3d12umddi-pfnd3d12ddi_dispatch_graph_0084.md)
