---
UID: NS:d3d12umddi.D3D12DDI_HIT_GROUP_DESC_0054
title: D3D12DDI_HIT_GROUP_DESC_0054 (d3d12umddi.h)
description: Describes a hit group.
ms.assetid: 026710fe-8976-4d56-a86e-1284581c3f70
ms.date: 10/19/2018
ms.topic: struct
f1_keywords:
 - "d3d12umddi/D3D12DDI_HIT_GROUP_DESC_0054"
ms.keywords: D3D12DDI_HIT_GROUP_DESC_0054, D3D12DDI_HIT_GROUP_DESC_0054, 
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
req.typenames: D3D12DDI_HIT_GROUP_DESC_0054
topic_type: 
- apiref
api_type: 
- HeaderDef
api_location: 
- d3d12umddi.h
api_name: 
- D3D12DDI_HIT_GROUP_DESC_0054
product:
- Windows
targetos: Windows
tech.root: display
ms.custom: RS5
---

# D3D12DDI_HIT_GROUP_DESC_0054 structure

## -description

Describes a hit group.

## -struct-fields

### -field HitGroupExport

Name of the hit group.

### -field Type

A [D3D12DDI_HIT_GROUP_TYPE](ne-d3d12umddi-d3d12ddi_hit_group_type.md) enumeration that represents the type of hit group.

### -field AnyHitShaderImport

The any hit shader import.

### -field ClosestHitShaderImport

Closest hit shader import.

### -field IntersectionShaderImport

Intersection shader import.

### -field SummaryFlags
 
A [D3D12DDI_EXPORT_SUMMARY_FLAGS](ne-d3d12umddi-d3d12ddi_export_summary_flags.md) flag that indicates the properties the runtime has determined about the shader export.

## -remarks

A hit group is one or more shaders that consists of: 

* 0 or 1 intersection shader
* 0 or 1 any hit shader
* 0 or 1 closest hit shader

Individual geometries in a given instance each refer to a hit group to provide their shader code. The point of the grouping is to allow implementations to be able to compile and execute the group as efficiently as rays interacting with geometry

Ray generation shaders and miss shaders aren’t part of hit groups because they aren’t involved directly with geometry.

If a hit group contains an intersection shader, it can only be used with procedural primitive geometry. If a hit group does not contain an intersection shader, it can only be used with triangle geometry.

A hit group with no shaders at all is also possible, by simply using NULL as it’s shader identifier.  

An empty hit group can be useful, for example, if the app doesn’t want to do anything for hits and only cares about the miss shader running when nothing has been hit.

## -see-also
