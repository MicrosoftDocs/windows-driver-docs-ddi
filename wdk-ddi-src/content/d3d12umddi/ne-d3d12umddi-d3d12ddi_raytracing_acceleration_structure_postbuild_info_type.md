---
UID: NE:d3d12umddi.D3D12DDI_RAYTRACING_ACCELERATION_STRUCTURE_POSTBUILD_INFO_TYPE
title: D3D12DDI_RAYTRACING_ACCELERATION_STRUCTURE_POSTBUILD_INFO_TYPE
author: windows-driver-content
description: Specifies the space requirements info for a ray tracing acceleration structure post build.
ms.assetid: 4ab1b4b8-dcf2-4211-bf2f-b94a0f115d00
ms.author: windowsdriverdev
ms.date: 
ms.topic: enum
ms.keywords: D3D12DDI_RAYTRACING_ACCELERATION_STRUCTURE_POSTBUILD_INFO_TYPE, D3D12DDI_RAYTRACING_ACCELERATION_STRUCTURE_POSTBUILD_INFO_TYPE, 
ms.prod: windows-hardware
ms.technology: windows-devices
req.header: d3d12umddi.h
req.include-header:
req.target-type:
req.target-min-winverclnt: Windows 10, version 1809
req.target-min-winversvr:
req.kmdf-ver:
req.umdf-ver:
req.ddi-compliance:
req.max-support:
req.typenames: D3D12DDI_RAYTRACING_ACCELERATION_STRUCTURE_POSTBUILD_INFO_TYPE
topic_type: 
-	apiref
api_type: 
-	HeaderDef
api_location: 
-	d3d12umddi.h
api_name: 
-	D3D12DDI_RAYTRACING_ACCELERATION_STRUCTURE_POSTBUILD_INFO_TYPE
product:
-	Windows
targetos: Windows
tech.root: display
---

# D3D12DDI_RAYTRACING_ACCELERATION_STRUCTURE_POSTBUILD_INFO_TYPE enumeration

## -description

Specifies the space requirements info for a ray tracing acceleration structure post build.

## -enum-fields

### -field D3D12DDI_RAYTRACING_ACCELERATION_STRUCTURE_POSTBUILD_INFO_COMPACTED_SIZE

Space requirements for an acceleration structure after compaction.

### -field D3D12DDI_RAYTRACING_ACCELERATION_STRUCTURE_POSTBUILD_INFO_TOOLS_VISUALIZATION

Space requirements for generating tools visualization for an acceleration structure (used by tools).

### -field D3D12DDI_RAYTRACING_ACCELERATION_STRUCTURE_POSTBUILD_INFO_SERIALIZATION

Space requirements for serializing an acceleration structure (used by tools).

### -field D3D12DDI_RAYTRACING_ACCELERATION_STRUCTURE_POSTBUILD_INFO_CURRENT_SIZE 

Space requirements for the current size.

## -remarks

## -see-also