---
UID: NE:d3d12umddi.D3D12DDI_STATE_SUBOBJECT_TYPE
title: D3D12DDI_STATE_SUBOBJECT_TYPE (d3d12umddi.h)
description: Learn more about the D3D12DDI_STATE_SUBOBJECT_TYPE enumeration.
ms.date: 05/03/2024
keywords: ["D3D12DDI_STATE_SUBOBJECT_TYPE enumeration"]
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
targetos: Windows
tech.root: display
ms.custom: RS5
f1_keywords:
 - D3D12DDI_STATE_SUBOBJECT_TYPE
 - d3d12umddi/D3D12DDI_STATE_SUBOBJECT_TYPE
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - d3d12umddi.h
api_name:
 - D3D12DDI_STATE_SUBOBJECT_TYPE
dev_langs:
 - c++
---

# D3D12DDI_STATE_SUBOBJECT_TYPE enumeration

## -description

The **D3D12DDI_STATE_SUBOBJECT_TYPE** enumeration specifies the supported subobject types within a Direct3D12 state object. The structure that [**D3D12DDI_STATE_SUBOBJECT_0054**](ns-d3d12umddi-d3d12ddi_state_subobject_0054.md)'s **pDesc** member points to is determined by the **D3D12DDI_STATE_SUBOBJECT_TYPE** enumeration value specified in its **Type** member.

## -enum-fields

### -field D3D12DDI_STATE_SUBOBJECT_TYPE_STATE_OBJECT_CONFIG

The configuration state of the subobject.

### -field D3D12DDI_STATE_SUBOBJECT_TYPE_GLOBAL_ROOT_SIGNATURE

The global root signatures.

### -field D3D12DDI_STATE_SUBOBJECT_TYPE_LOCAL_ROOT_SIGNATURE:2

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

* 0 or 1 intersection shader
* 0 or 1 any hit shader
* 0 or 1 closest hit shader

### -field D3D12DDI_STATE_SUBOBJECT_TYPE_WORK_GRAPH

Subobject type is a work graph; **pDesc** points to a [**D3D12DDI_WORK_GRAPH_DESC_0108**](ns-d3d12umddi-d3d12ddi_work_graph_desc_0108.md) structure.

### -field D3D12DDI_STATE_SUBOBJECT_TYPE_STREAM_OUTPUT

Subobject type is stream output.

### -field D3D12DDI_STATE_SUBOBJECT_TYPE_BLEND

Subject type is blend.

### -field D3D12DDI_STATE_SUBOBJECT_TYPE_SAMPLE_MASK

### -field D3D12DDI_STATE_SUBOBJECT_TYPE_RASTERIZER

### -field D3D12DDI_STATE_SUBOBJECT_TYPE_DEPTH_STENCIL

### -field D3D12DDI_STATE_SUBOBJECT_TYPE_INPUT_LAYOUT

### - D3D12DDI_STATE_SUBOBJECT_TYPE_IB_STRIP_CUT_VALUE

### -field D3D12DDI_STATE_SUBOBJECT_TYPE_PRIMITIVE_TOPOLOGY

### -field D3D12DDI_STATE_SUBOBJECT_TYPE_RENDER_TARGET_FORMATS

### - D3D12DDI_STATE_SUBOBJECT_TYPE_DEPTH_STENCIL_FORMAT

### -field D3D12DDI_STATE_SUBOBJECT_TYPE_SAMPLE_DESC

### -field D3D12DDI_STATE_SUBOBJECT_TYPE_FLAGS

### -field D3D12DDI_STATE_SUBOBJECT_TYPE_VIEW_INSTANCING

### -field D3D12DDI_STATE_SUBOBJECT_TYPE_GENERIC_PROGRAM

### -field D3D12DDI_STATE_SUBOBJECT_TYPE_SHADER_EXPORT_SUMMARY

The export summary configuration.

## -remarks

State objects have a type that dictates rules about the subobjects they contain and how the state objects can be used.

## -see-also

[**D3D12DDI_STATE_OBJECT_TYPE**](ne-d3d12umddi-d3d12ddi_state_object_type.md)

[**D3D12DDI_STATE_SUBOBJECT_0054**](ns-d3d12umddi-d3d12ddi_state_subobject_0054.md)

[**PFND3D12DDI_CREATE_STATE_OBJECT_0054**](nc-d3d12umddi-pfnd3d12ddi_create_state_object_0054.md)
