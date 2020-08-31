---
UID: NS:d3d12umddi.D3D12DDI_RAYTRACING_ACCELERATION_STRUCTURE_POSTBUILD_INFO_SERIALIZATION_DESC_0054
title: D3D12DDI_RAYTRACING_ACCELERATION_STRUCTURE_POSTBUILD_INFO_SERIALIZATION_DESC_0054 (d3d12umddi.h)
description: Space requirements for serializing a ray tracing acceleration structure used by tools.
ms.assetid: f98cd914-ab0f-4433-8634-2c9236eb5402
ms.date: 10/19/2018
keywords: ["D3D12DDI_RAYTRACING_ACCELERATION_STRUCTURE_POSTBUILD_INFO_SERIALIZATION_DESC_0054 structure"]
ms.keywords: D3D12DDI_RAYTRACING_ACCELERATION_STRUCTURE_POSTBUILD_INFO_SERIALIZATION_DESC_0054, D3D12DDI_RAYTRACING_ACCELERATION_STRUCTURE_POSTBUILD_INFO_SERIALIZATION_DESC_0054,
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
req.typenames: D3D12DDI_RAYTRACING_ACCELERATION_STRUCTURE_POSTBUILD_INFO_SERIALIZATION_DESC_0054
targetos: Windows
tech.root: display
ms.custom: RS5
f1_keywords:
 - D3D12DDI_RAYTRACING_ACCELERATION_STRUCTURE_POSTBUILD_INFO_SERIALIZATION_DESC_0054
 - d3d12umddi/D3D12DDI_RAYTRACING_ACCELERATION_STRUCTURE_POSTBUILD_INFO_SERIALIZATION_DESC_0054
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - d3d12umddi.h
api_name:
 - D3D12DDI_RAYTRACING_ACCELERATION_STRUCTURE_POSTBUILD_INFO_SERIALIZATION_DESC_0054
dev_langs:
 - c++
---

# D3D12DDI_RAYTRACING_ACCELERATION_STRUCTURE_POSTBUILD_INFO_SERIALIZATION_DESC_0054 structure


## -description

Space requirements for serializing a ray tracing acceleration structure used by tools.

## -struct-fields

### -field SerializedSizeInBytes

Size of the serialized acceleration structure, including a [D3D12DDI_SERIALIZED_RAYTRACING_ACCELERATION_STRUCTURE_HEADER_0054](ns-d3d12umddi-d3d12ddi_serialized_raytracing_acceleration_structure_header_0054.md) header.

### -field NumBottomLevelAccelerationStructurePointers

 
Specifies how many 64-bit GPUVAs (graphical processing unit virtual address) will be at the start of the serialized acceleration structure. For a bottom-level acceleration structure this will be 0. For a top-level acceleration structure, the pointers indicate the acceleration structures being referred to. When deserializing happens, these pointers must be initialized by the app in the serialized data, just after the header, to the new locations of the equivalent acceleration structures. These new locations pointed to at deserialize time need not have been populated with bottom level acceleration structures yet, as long as they have been initialized with the expected deserialized data structures before use in raytracing. During deserialization, the driver reads the new pointers, using them to produce an equivalent top-level acceleration structure to the original.

## -remarks

## -see-also

