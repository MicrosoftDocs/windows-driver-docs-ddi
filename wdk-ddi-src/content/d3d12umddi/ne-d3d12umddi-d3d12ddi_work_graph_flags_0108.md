---
UID: NE:d3d12umddi.D3D12DDI_WORK_GRAPH_FLAGS_0108
tech.root: display
title: D3D12DDI_WORK_GRAPH_FLAGS_0108
ms.date: 05/03/2024
targetos: Windows
description: Learn more about the D3D12DDI_WORK_GRAPH_FLAGS_0108 enumeration.
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
 - D3D12DDI_WORK_GRAPH_FLAGS_0108
f1_keywords:
 - D3D12DDI_WORK_GRAPH_FLAGS_0108
 - d3d12umddi/D3D12DDI_WORK_GRAPH_FLAGS_0108
dev_langs:
 - c++
helpviewer_keywords:
 - D3D12DDI_WORK_GRAPH_FLAGS_0108
---

# D3D12DDI_WORK_GRAPH_FLAGS_0108 enumeration (d3d12umddi.h)

## -description

The **D3D12DDI_WORK_GRAPH_FLAGS_0108** enumeration specifies flags for the [**D3D12DDI_WORK_GRAPH_DESC_0108**](ns-d3d12umddi-d3d12ddi_work_graph_desc_0108.md) structure for configuring the behavior of the work graph.

## -enum-fields

### -field D3D12DDI_WORK_GRAPH_FLAG_NONE

Default behavior.

### -field D3D12DDI_WORK_GRAPH_FLAG_ADD_TO_EXISTING_WORK_GRAPH

The work graph is being added to an existing one, so the **ProgramName** has been seen before. It is possible for  [**PFND3D12DDI_ADD_TO_STATE_OBJECT_0072**](nc-d3d12umddi-pfnd3d12ddi_add_to_state_object_0072.md) to be used without this flag, in which case an entirely new work graph is being added to the state object, such as making a new graph from some existing or new nodes in the state object. So this flag helps distinguish adding an entirely new state object versus adding to an existing one.

The driver could also deduce this by checking to see if **ProgramName** already exists in the state object, but the flag saves the trouble. Whether or not this flag is present, the work graph description lists the entire graph, with newly added nodes at the start of the list (reusing list entries for existing nodes). Newly added node definitions include pointers for how they are connected to the rest of the graph (just like existing nodes), and existing nodes provided in previous state objects are updated in-place to link back to the new nodes they are connected to. So there is one representation of all versions of the graph together, and the differences between versions can be seen by the **Version** number in each node. For the rules about valid additions, see [**PFND3D12DDI_ADD_TO_STATE_OBJECT_0072**](nc-d3d12umddi-pfnd3d12ddi_add_to_state_object_0072.md).

## -remarks

For more information, see [Work graphs](/windows-hardware/drivers/display/work-graphs).

## -see-also

[**D3D12DDI_WORK_GRAPH_DESC_0108**](ns-d3d12umddi-d3d12ddi_work_graph_desc_0108.md)
