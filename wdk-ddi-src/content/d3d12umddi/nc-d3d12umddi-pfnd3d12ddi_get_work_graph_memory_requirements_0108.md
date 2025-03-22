---
UID: NC:d3d12umddi.PFND3D12DDI_GET_WORK_GRAPH_MEMORY_REQUIREMENTS_0108
tech.root: display
title: PFND3D12DDI_GET_WORK_GRAPH_MEMORY_REQUIREMENTS_0108
ms.date: 05/03/2024
targetos: Windows
description: Learn more about the PFND3D12DDI_GET_WORK_GRAPH_MEMORY_REQUIREMENTS_0108 function.
prerelease: false
req.assembly: 
req.construct-type: function
req.ddi-compliance: 
req.dll: 
req.header: d3d12umddi.h
req.idl: 
req.include-header: 
req.irql: 
req.kmdf-ver: 
req.lib: 
req.max-support: 
req.namespace: 
req.redist: 
req.target-min-winverclnt: Windows 11, version 24H2 (WDDM 3.2)
req.target-min-winversvr: 
req.target-type: 
req.type-library: 
req.umdf-ver: 
req.unicode-ansi: 
topic_type:
 - apiref
api_type:
 - LibDef
api_location:
 - d3d12umddi.h
api_name:
 - PFND3D12DDI_GET_WORK_GRAPH_MEMORY_REQUIREMENTS_0108
f1_keywords:
 - PFND3D12DDI_GET_WORK_GRAPH_MEMORY_REQUIREMENTS_0108
 - d3d12umddi/PFND3D12DDI_GET_WORK_GRAPH_MEMORY_REQUIREMENTS_0108
dev_langs:
 - c++
helpviewer_keywords:
 - PFND3D12DDI_GET_WORK_GRAPH_MEMORY_REQUIREMENTS_0108
---

# PFND3D12DDI_GET_WORK_GRAPH_MEMORY_REQUIREMENTS_0108 function (d3d12umddi.h)

## -description

The user-mode driver's **pfnGetWorkGraphMemoryRequirements** function gets the backing memory size requirements for a work graph.

## -parameters

### -param unnamedParam1

[in] A [**D3D12DDI_HSTATEOBJECT_0054**](nc-d3d12umddi-pfnd3d12ddi_create_state_object_0054.md) handle to the state object for which the memory requirements are being queried.

### -param pProgramName

[in] Pointer to a string that contains the name of the work graph which to retrieve memory requirements.

### -param pRequirements

[out] Pointer to a [**D3D12DDI_WORK_GRAPH_MEMORY_REQUIREMENTS_0108**](ns-d3d12umddi-d3d12ddi_work_graph_memory_requirements_0108.md) structure in which to return the backing memory size requirements for the work graph.

## -remarks

For more information, see [Work graphs](/windows-hardware/drivers/display/work-graphs).

## -see-also

[**D3D12DDI_WORK_GRAPH_MEMORY_REQUIREMENTS_0108**](ns-d3d12umddi-d3d12ddi_work_graph_memory_requirements_0108.md)
