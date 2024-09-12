---
UID: NE:d3d12umddi.D3D12DDI_SET_WORK_GRAPH_FLAGS_0084
tech.root: display
title: D3D12DDI_SET_WORK_GRAPH_FLAGS_0084
ms.date: 09/09/2024
targetos: Windows
description: Learn more about the D3D12DDI_SET_WORK_GRAPH_FLAGS_0084 enumeration.
prerelease: false
req.construct-type: enumeration
req.ddi-compliance: 
req.header: d3d12umddi.h
req.include-header: 
req.kmdf-ver: 
req.max-support: 
req.target-min-winverclnt:
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
 - D3D12DDI_SET_WORK_GRAPH_FLAGS_0084
f1_keywords:
 - D3D12DDI_SET_WORK_GRAPH_FLAGS_0084
 - d3d12umddi/D3D12DDI_SET_WORK_GRAPH_FLAGS_0084
dev_langs:
 - c++
helpviewer_keywords:
 - D3D12DDI_SET_WORK_GRAPH_FLAGS_0084
---

## -description

The **D3D12DDI_SET_WORK_GRAPH_FLAGS_0084** enumeration specifies flags for setting the work graph.

## -enum-fields

### -field D3D12DDI_SET_WORK_GRAPH_FLAG_NONE_0084

Indicates default behavior.

### -field D3D12DDI_SET_WORK_GRAPH_FLAG_INITIALIZE_0084

Prepare backing store memory for an initial dispatch. This flag is set the first time a work graph is used with a particular backing memory allocation.

## -remarks

For more information, see [Work graphs](/windows-hardware/drivers/display/work-graphs).

## -see-also

[**D3D12DDI_SET_WORK_GRAPH_DESC_0084**](ns-d3d12umddi-d3d12ddi_set_work_graph_desc_0084.md)

[**PFND3D12DDI_SET_PROGRAM_0084**](nc-d3d12umddi-pfnd3d12ddi_set_program_0084.md)