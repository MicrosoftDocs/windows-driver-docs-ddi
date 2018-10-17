---
UID: NE:d3d12umddi.D3D12DDI_RAYTRACING_ACCELERATION_STRUCTURE_TYPE
title: D3D12DDI_RAYTRACING_ACCELERATION_STRUCTURE_TYPE
author: windows-driver-content
description: Specifies the ray tracing acceleration structure type.
ms.assetid: 53711cae-d866-454d-a166-4bf1ca26900f
ms.date: 
ms.topic: enum
ms.keywords: D3D12DDI_RAYTRACING_ACCELERATION_STRUCTURE_TYPE, D3D12DDI_RAYTRACING_ACCELERATION_STRUCTURE_TYPE, 
req.header: d3d12umddi.h
req.include-header:
req.target-type:
req.target-min-winverclnt: Windows 10, version 1809
req.target-min-winversvr:
req.kmdf-ver:
req.umdf-ver:
req.ddi-compliance:
req.max-support:
req.typenames: D3D12DDI_RAYTRACING_ACCELERATION_STRUCTURE_TYPE
topic_type: 
-	apiref
api_type: 
-	HeaderDef
api_location: 
-	d3d12umddi.h
api_name: 
-	D3D12DDI_RAYTRACING_ACCELERATION_STRUCTURE_TYPE
product:
-	Windows
targetos: Windows
tech.root: display
---

# D3D12DDI_RAYTRACING_ACCELERATION_STRUCTURE_TYPE enumeration

## -description

Specifies the ray tracing acceleration structure type.

## -enum-fields

### -field D3D12DDI_RAYTRACING_ACCELERATION_STRUCTURE_TYPE_TOP_LEVEL

Top-level acceleration structure.

### -field D3D12DDI_RAYTRACING_ACCELERATION_STRUCTURE_TYPE_BOTTOM_LEVEL

Bottom-level acceleration structure.

## -remarks

Geometry for a scene is described to the system using two levels of acceleration structures:  

* Bottom-level acceleration structures each consist of a set of geometries that are building blocks for a scene.  
* A top-level acceleration structure represents a set of instances of bottom-level acceleration structures. 

Within a given bottom-level acceleration structure there can be any number either: 

1. triangle meshes
2. procedural primitives initially described only by an axis-aligned bounding box (AABB)

## -see-also
