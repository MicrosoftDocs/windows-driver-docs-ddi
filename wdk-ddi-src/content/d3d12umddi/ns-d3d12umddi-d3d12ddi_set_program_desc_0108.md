---
UID: NS:d3d12umddi.D3D12DDI_SET_PROGRAM_DESC_0108
tech.root: display
title: D3D12DDI_SET_PROGRAM_DESC_0108
ms.date: 05/03/2024
targetos: Windows
description: Learn more about the D3D12DDI_SET_PROGRAM_DESC_0108 structure.
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
req.typenames: D3D12DDI_SET_PROGRAM_DESC_0108
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
 - D3D12DDI_SET_PROGRAM_DESC_0108
f1_keywords:
 - D3D12DDI_SET_PROGRAM_DESC_0108
 - d3d12umddi/D3D12DDI_SET_PROGRAM_DESC_0108
dev_langs:
 - c++
helpviewer_keywords:
 - D3D12DDI_SET_PROGRAM_DESC_0108
---

# D3D12DDI_SET_PROGRAM_DESC_0108 structure (d3d12umddi.h)

## -description

The **D3D12DDI_SET_PROGRAM_DESC_0108** structure describes the program that [**PFND3D12DDI_SET_PROGRAM_0108**](nc-d3d12umddi-pfnd3d12ddi_set_program_0108.md) should set on a command list.

## -struct-fields

### -field Type

A [**D3D12DDI_PROGRAM_TYPE_0108**](ne-d3d12umddi-d3d12ddi_program_type_0108.md) enumeration that specifies the type of program to set.

### -field GenericPipeline

A [**D3D12DDI_SET_GENERIC_PIPELINE_DESC_0108**](ns-d3d12umddi-d3d12ddi_set_generic_pipeline_desc_0108.md) structure that describes the generic pipeline to set when **Type** is **D3D12DDI_PROGRAM_TYPE_GENERIC_PIPELINE_0108**.

### -field RaytracingPipeline

A [**D3D12DDI_SET_RAYTRACING_PIPELINE_DESC_0108**](ns-d3d12umddi-d3d12ddi_set_raytracing_pipeline_desc_0108.md) structure that describes the raytracing pipeline to set when **Type** is **D3D12DDI_PROGRAM_TYPE_RAYTRACING_PIPELINE_0108**. Not currently supported.

### -field WorkGraph

A [**D3D12DDI_SET_WORK_GRAPH_DESC_0108**](ns-d3d12umddi-d3d12ddi_set_work_graph_desc_0108.md) structure that describes the work graph to set when **Type** is **D3D12DDI_PROGRAM_TYPE_WORK_GRAPH_0108**.

## -remarks

For more information, see [Work graphs](/windows-hardware/drivers/display/work-graphs).

## -see-also

[**D3D12DDI_PROGRAM_TYPE_0108**](ne-d3d12umddi-d3d12ddi_program_type_0108.md)

[**D3D12DDI_SET_GENERIC_PIPELINE_DESC_0108**](ns-d3d12umddi-d3d12ddi_set_generic_pipeline_desc_0108.md)

[**D3D12DDI_SET_RAYTRACING_PIPELINE_DESC_0108**](ns-d3d12umddi-d3d12ddi_set_raytracing_pipeline_desc_0108.md)

[**D3D12DDI_SET_WORK_GRAPH_DESC_0108**](ns-d3d12umddi-d3d12ddi_set_work_graph_desc_0108.md)

[**PFND3D12DDI_SET_PROGRAM_0108**](nc-d3d12umddi-pfnd3d12ddi_set_program_0108.md)
