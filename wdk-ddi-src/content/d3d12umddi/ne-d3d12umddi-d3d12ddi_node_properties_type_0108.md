---
UID: NE:d3d12umddi.D3D12DDI_NODE_PROPERTIES_TYPE_0108
tech.root: display
title: D3D12DDI_NODE_PROPERTIES_TYPE_0108
ms.date: 05/03/2024
targetos: Windows
description: Learn more about the D3D12DDI_NODE_PROPERTIES_TYPE_0108 enumeration.
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
 - D3D12DDI_NODE_PROPERTIES_TYPE_0108
f1_keywords:
 - D3D12DDI_NODE_PROPERTIES_TYPE_0108
 - d3d12umddi/D3D12DDI_NODE_PROPERTIES_TYPE_0108
dev_langs:
 - c++
helpviewer_keywords:
 - D3D12DDI_NODE_PROPERTIES_TYPE_0108
---

# D3D12DDI_NODE_PROPERTIES_TYPE_0108 enumeration (d3d12umddi.h)

## -description

The **D3D12DDI_NODE_PROPERTIES_TYPE_0108** enumeration specifies the type of properties associated with a node in a work graph.

## -enum-fields

### -field D3D12DDI_NODE_PROPERTIES_TYPE_BROADCASTING_LAUNCH_0108

Indicates that the node properties are related to a broadcasting launch node (one input seen by many thread groups).

### -field D3D12DDI_NODE_PROPERTIES_TYPE_COALESCING_LAUNCH_0108

Indicates that the node properties are related to a coalescing launch node (variable inputs seen by each thread group).

### -field D3D12DDI_NODE_PROPERTIES_TYPE_THREAD_LAUNCH_0108

Indicates that the node properties are related to a thread launch node (one input per thread).

## -remarks

For more information, see [Work graphs](/windows-hardware/drivers/display/work-graphs).

## -see-also

[**D3D12DDI_SHADER_NODE_0108**](ns-d3d12umddi-d3d12ddi_shader_node_0108.md)
