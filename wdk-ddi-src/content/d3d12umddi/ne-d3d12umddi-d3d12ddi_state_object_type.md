---
UID: NE:d3d12umddi.D3D12DDI_STATE_OBJECT_TYPE
title: D3D12DDI_STATE_OBJECT_TYPE
author: windows-driver-content
description: The state object types.
ms.assetid: 2ae86b8b-5dbd-49a8-89a2-7991506060e2
ms.date: 10/19/2018
ms.topic: enum
ms.keywords: D3D12DDI_STATE_OBJECT_TYPE, D3D12DDI_STATE_OBJECT_TYPE, 
req.header: d3d12umddi.h
req.include-header:
req.target-type:
req.target-min-winverclnt: Windows 10, version 1809
req.target-min-winversvr:
req.kmdf-ver:
req.umdf-ver:
req.ddi-compliance:
req.max-support:
req.typenames: D3D12DDI_STATE_OBJECT_TYPE
topic_type: 
-	apiref
api_type: 
-	HeaderDef
api_location: 
-	d3d12umddi.h
api_name: 
-	D3D12DDI_STATE_OBJECT_TYPE
product:
-	Windows
targetos: Windows
tech.root: display
---

# D3D12DDI_STATE_OBJECT_TYPE enumeration

## -description

State objects have a type that dictates rules about the subobjects they contain and how the state objects can be used.

## -enum-fields

### -field D3D12DDI_STATE_OBJECT_TYPE_COLLECTION

A collection can contain any amount of subobjects, but doesn’t have constraints. Not all dependencies that the included subobjects have must be resolved in the same collection  Even if dependencies are locally defined, the set of subobjects doesn’t have to be the complete set of state that will eventually be used on the GPU. For instance, a collection may not include all shaders needed to *raytrace* a scene, though it could.

The purpose of a collection is to allow an application to pass an arbitrarily large or small collection of state to drivers to compile at once (e.g. on a given thread).

### -field D3D12DDI_STATE_OBJECT_TYPE_RAYTRACING_PIPELINE 

An RTPSO (ray tracing pipeline state object) represents a full set of shaders that could be reachable by a DispatchRays() call, with all configuration options resolved, such as local root signatures and other state.  

An RTPSO can be thought of as an *executable* state object.

## -remarks

## -see-also
