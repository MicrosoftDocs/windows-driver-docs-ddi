---
UID: NS:d3d12umddi.D3D12DDI_NODE_ID_0108
tech.root: display
title: D3D12DDI_NODE_ID_0108
ms.date: 05/03/2024
targetos: Windows
description: Learn more about the D3D12DDI_NODE_ID_0108 structure.
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
req.typenames: D3D12DDI_NODE_ID_0108
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
 - D3D12DDI_NODE_ID_0108
f1_keywords:
 - D3D12DDI_NODE_ID_0108
 - d3d12umddi/D3D12DDI_NODE_ID_0108
dev_langs:
 - c++
helpviewer_keywords:
 - D3D12DDI_NODE_ID_0108
---

# D3D12DDI_NODE_ID_0108 structure (d3d12umddi.h)

## -description

The **D3D12DDI_NODE_ID_0108** structure specifies the ID of a node in a work graph.

## -struct-fields

### -field Name

The string part of the node ID.

### -field ArrayIndex

Array index part of Node ID (defaults to 0 if not specified in HLSL)

## -remarks

See [Node ID](https://github.com/microsoft/DirectX-Specs/blob/master/d3d/WorkGraphs.md#node-id) for more information.

## -see-also

[**D3D12DDI_BROADCASTING_LAUNCH_NODE_PROPERTIES_0108**](ns-d3d12umddi-d3d12ddi_broadcasting_launch_node_properties_0108.md)

[D3D12DDI_COALESCING_LAUNCH_NODE_PROPERTIES_0108](ns-d3d12umddi-d3d12ddi_coalescing_launch_node_properties_0108.md)

[**D3D12DDI_NODE_OUTPUT_0108**](ns-d3d12umddi-d3d12ddi_node_output_0108.md)

[**D3D12DDI_SHADER_NODE_0108**](ns-d3d12umddi-d3d12ddi_shader_node_0108.md)

[**D3D12DDI_THREAD_LAUNCH_NODE_PROPERTIES_0108**](ns-d3d12umddi-d3d12ddi_thread_launch_node_properties_0108.md)
