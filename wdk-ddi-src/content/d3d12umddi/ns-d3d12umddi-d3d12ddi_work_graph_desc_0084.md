---
UID: NS:d3d12umddi.D3D12DDI_WORK_GRAPH_DESC_0084
tech.root: display
title: D3D12DDI_WORK_GRAPH_DESC_0084
ms.date: 09/09/2024
targetos: Windows
description: Learn more about the D3D12DDI_WORK_GRAPH_DESC_0084 structure.
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
req.typenames: D3D12DDI_WORK_GRAPH_DESC_0084
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
 - D3D12DDI_WORK_GRAPH_DESC_0084
f1_keywords:
 - D3D12DDI_WORK_GRAPH_DESC_0084
 - d3d12umddi/D3D12DDI_WORK_GRAPH_DESC_0084
dev_langs:
 - c++
helpviewer_keywords:
 - D3D12DDI_WORK_GRAPH_DESC_0084
---

## -description

The **D3D12DDI_WORK_GRAPH_DESC_0084** structure defines the state subobject of type [**D3D12DDI_STATE_SUBOBJECT_TYPE_WORK_GRAPH**](ne-d3d12umddi-d3d12ddi_state_subobject_type.md).

## -struct-fields

### -field ProgramName

Name of the work graph. This name is unique in the given state object.

### -field NumNodes

The number of nodes in the work graph, including already existing ones if an addition is happening. This value determines the elements in the **pNodes** array.

### -field ppNodes

Pointer to a pointer to an array of [**D3D12DDI_NODE_0084**](ns-d3d12umddi-d3d12ddi_node_0084.md) structures that describe the nodes in the work graph.

### -field NumEntrypoints

Number of entrypoints including already existing ones if an addition is happening. This value determines the number of elements in the **pEntrypoints** array.

### -field pEntrypointNodeIndices

Pointer to an array of indices into the **pNodes** array that specify the entrypoints for the work graph.

## -remarks

For more information, see [Work graphs](/windows-hardware/drivers/display/work-graphs).

## -see-also

[**D3D12DDI_NODE_0084**](ns-d3d12umddi-d3d12ddi_node_0084.md)

[**D3D12DDI_STATE_SUBOBJECT_TYPE_WORK_GRAPH**](ne-d3d12umddi-d3d12ddi_state_subobject_type.md)

[**PFND3D12DDI_ADD_TO_STATE_OBJECT_0072**](nc-d3d12umddi-pfnd3d12ddi_add_to_state_object_0072.md)

[**PFND3D12DDI_CREATE_STATE_OBJECT_0054**](nc-d3d12umddi-pfnd3d12ddi_create_state_object_0054.md)

[**PFND3D12DDI_DISPATCH_GRAPH_0084**](nc-d3d12umddi-pfnd3d12ddi_dispatch_graph_0084.md)
