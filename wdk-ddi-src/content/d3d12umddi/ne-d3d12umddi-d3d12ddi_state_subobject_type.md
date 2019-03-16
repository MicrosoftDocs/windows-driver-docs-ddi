---
UID: NE:d3d12umddi.D3D12DDI_STATE_SUBOBJECT_TYPE
title: D3D12DDI_STATE_SUBOBJECT_TYPE (d3d12umddi.h)
description: The supported state subobject types.
ms.assetid: 374a2d3d-313f-4e23-b6ad-8137e19230df
ms.date: 10/19/2018
ms.topic: enum
ms.keywords: D3D12DDI_STATE_SUBOBJECT_TYPE, D3D12DDI_STATE_SUBOBJECT_TYPE, ray tracing
req.header: d3d12umddi.h
req.include-header:
req.target-type:
req.target-min-winverclnt: Windows 10, version 1809
req.target-min-winversvr:
req.kmdf-ver:
req.umdf-ver:
req.ddi-compliance:
req.max-support:
req.typenames: D3D12DDI_STATE_SUBOBJECT_TYPE
topic_type: 
- apiref
api_type: 
- HeaderDef
api_location: 
- d3d12umddi.h
api_name: 
- D3D12DDI_STATE_SUBOBJECT_TYPE
product:
- Windows
targetos: Windows
tech.root: display
ms.custom: RS5
---

# D3D12DDI_STATE_SUBOBJECT_TYPE enumeration

## -description

The supported state subobject types.

## -enum-fields

### -field D3D12DDI_STATE_SUBOBJECT_TYPE_STATE_OBJECT_CONFIG

The configuration state of the subobject.

### -field D3D12DDI_STATE_SUBOBJECT_TYPE_GLOBAL_ROOT_SIGNATURE

The global root signatures.

### -field D3D12DDI_STATE_SUBOBJECT_TYPE_LOCAL_ROOT_SIGNATURE

The local root signatures.

### -field D3D12DDI_STATE_SUBOBJECT_TYPE_NODE_MASK

The node mask.

### -field D3D12DDI_STATE_SUBOBJECT_TYPE_DXIL_LIBRARY

The DXIL (DirectX Intermediate Language) library.

### -field D3D12DDI_STATE_SUBOBJECT_TYPE_EXISTING_COLLECTION

The existing collection.

### -field D3D12DDI_STATE_SUBOBJECT_TYPE_RAYTRACING_SHADER_CONFIG

The ray tracing shader configuration.

### -field D3D12DDI_STATE_SUBOBJECT_TYPE_RAYTRACING_PIPELINE_CONFIG

The ray tracing pipeline configuration.

### -field D3D12DDI_STATE_SUBOBJECT_TYPE_HIT_GROUP

The HIT group configuration. A hit group is one or more shaders consisting of: 
<br/>
- 0 or 1 intersection shader<br/>
- 0 or 1 any hit shader<br/>
- 0 or 1 closest hit shader

### -field D3D12DDI_STATE_SUBOBJECT_TYPE_SHADER_EXPORT_SUMMARY 

The export summary configuration.

## -remarks

## -see-also
