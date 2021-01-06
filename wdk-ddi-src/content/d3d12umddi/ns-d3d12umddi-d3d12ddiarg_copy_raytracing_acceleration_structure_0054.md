---
UID: NS:d3d12umddi.D3D12DDIARG_COPY_RAYTRACING_ACCELERATION_STRUCTURE_0054
title: D3D12DDIARG_COPY_RAYTRACING_ACCELERATION_STRUCTURE_0054 (d3d12umddi.h)
description: Arguments used in the CopyRayTracingAccelerationStructure callback function.
ms.date: 10/19/2018
keywords: ["D3D12DDIARG_COPY_RAYTRACING_ACCELERATION_STRUCTURE_0054 structure"]
ms.keywords: D3D12DDIARG_COPY_RAYTRACING_ACCELERATION_STRUCTURE_0054, D3D12DDIARG_COPY_RAYTRACING_ACCELERATION_STRUCTURE_0054,
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
req.typenames: D3D12DDIARG_COPY_RAYTRACING_ACCELERATION_STRUCTURE_0054
targetos: Windows
tech.root: display
ms.custom: RS5
f1_keywords:
 - D3D12DDIARG_COPY_RAYTRACING_ACCELERATION_STRUCTURE_0054
 - d3d12umddi/D3D12DDIARG_COPY_RAYTRACING_ACCELERATION_STRUCTURE_0054
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - d3d12umddi.h
api_name:
 - D3D12DDIARG_COPY_RAYTRACING_ACCELERATION_STRUCTURE_0054
dev_langs:
 - c++
---

# D3D12DDIARG_COPY_RAYTRACING_ACCELERATION_STRUCTURE_0054 structure


## -description

Arguments used in the [CopyRayTracingAccelerationStructure](nc-d3d12umddi-pfnd3d12ddi_copy_raytracing_acceleration_structure_0054.md) callback function.

## -struct-fields

### -field DestAccelerationStructureData

Destination memory. The required size can be discovered by calling [EmitRaytracingAccelerationStructurePostBuildInfo](nc-d3d12umddi-pfnd3d12ddi_emit_raytracing_acceleration_structure_postbuild_info_0054.md) beforehand, if necessary, depending on the *Mode*.  

Destination start address must be 256 byte aligned, regardless of the *Mode*.

Destination memory range cannot overlap source otherwise results are undefined.  

The resource state that the memory pointed to must be dependent on the *Mode* parameter. See [D3D12DDI_RAYTRACING_ACCELERATION_STRUCTURE_COPY_MODE](ne-d3d12umddi-d3d12ddi_raytracing_acceleration_structure_copy_mode.md).

### -field SourceAccelerationStructureData

Acceleration structure to copy or transform based on the specified *Mode*. The source acceleration structure remains unchanged and still usable. The operation only involves the source acceleration structure directly specified and not others it may point to. For example, in the case of a top-level acceleration structure, any bottom-level acceleration structures that it points to are not involved in the operation.

The resource state that the memory pointed to must be dependent on the *Mode* parameter. See [D3D12DDI_RAYTRACING_ACCELERATION_STRUCTURE_COPY_MODE](ne-d3d12umddi-d3d12ddi_raytracing_acceleration_structure_copy_mode.md).

### -field Mode

 
Type of copy operation to perform.

## -remarks

## -see-also

