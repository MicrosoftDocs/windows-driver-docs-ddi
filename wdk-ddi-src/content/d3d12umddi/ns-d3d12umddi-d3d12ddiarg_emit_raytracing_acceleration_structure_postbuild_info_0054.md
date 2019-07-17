---
UID: NS:d3d12umddi.D3D12DDIARG_EMIT_RAYTRACING_ACCELERATION_STRUCTURE_POSTBUILD_INFO_0054
title: D3D12DDIARG_EMIT_RAYTRACING_ACCELERATION_STRUCTURE_POSTBUILD_INFO_0054 (d3d12umddi.h)
description: Arguments used in the PFND3D12DDI_EMIT_RAYTRACING_ACCELERATION_STRUCTURE_POSTBUILD_INFO_0054 callback function.
ms.assetid: c33522e2-7500-4b79-acc0-f30369644a06
ms.date: 10/19/2018
ms.topic: struct
f1_keywords:
 - "d3d12umddi/D3D12DDIARG_EMIT_RAYTRACING_ACCELERATION_STRUCTURE_POSTBUILD_INFO_0054"
ms.keywords: D3D12DDIARG_EMIT_RAYTRACING_ACCELERATION_STRUCTURE_POSTBUILD_INFO_0054, D3D12DDIARG_EMIT_RAYTRACING_ACCELERATION_STRUCTURE_POSTBUILD_INFO_0054, 
req.header: d3d12umddi.h
req.include-header:
req.target-type:
req.target-min-winverclnt: Windows 10, version 1809
req.target-min-winversvr:
req.kmdf-ver:
req.umdf-ver:
req.lib:
req.dll:
req.ddi-compliance:
req.unicode-ansi:
req.max-support:
req.typenames: D3D12DDIARG_EMIT_RAYTRACING_ACCELERATION_STRUCTURE_POSTBUILD_INFO_0054
topic_type: 
- apiref
api_type: 
- HeaderDef
api_location: 
- d3d12umddi.h
api_name: 
- D3D12DDIARG_EMIT_RAYTRACING_ACCELERATION_STRUCTURE_POSTBUILD_INFO_0054
product:
- Windows
targetos: Windows
tech.root: display
ms.custom: RS5
---

# D3D12DDIARG_EMIT_RAYTRACING_ACCELERATION_STRUCTURE_POSTBUILD_INFO_0054 structure

## -description

Arguments used in the [PFND3D12DDI_EMIT_RAYTRACING_ACCELERATION_STRUCTURE_POSTBUILD_INFO_0054](nc-d3d12umddi-pfnd3d12ddi_emit_raytracing_acceleration_structure_postbuild_info_0054.md) callback function.

## -struct-fields

### -field Desc

A [D3D12DDI_RAYTRACING_ACCELERATION_STRUCTURE_POSTBUILD_INFO_DESC_0054](ns-d3d12umddi-d3d12ddi_raytracing_acceleration_structure_postbuild_info_desc_0054.md) structure.

### -field NumSourceAccelerationStructures

Number of pointers to acceleration structure GPUVAs (graphical processing unit virtual address) pointed to by *pSourceAccelerationStructureData*.  

This number also affects the destination (output), which will be a contiguous array of *NumSourceAccelerationStructures* output structures, where the type of the structures depends on *InfoType*.

### -field pSourceAccelerationStructureData

Pointer to array of GPUVAs of size *NumSourceAccelerationStructures*.  Each GPUVA points to the start of an existing acceleration structure.

The memory pointed to must be in [resource state](ne-d3d12umddi-d3d12ddi_resource_states.md) D3D12DDI_RESOURCE_STATE_RAYTRACING_ACCELERATION_STRUCTURE.

## -remarks

## -see-also
