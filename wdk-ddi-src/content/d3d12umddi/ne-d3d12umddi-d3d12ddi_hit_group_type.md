---
UID: NE:d3d12umddi.D3D12DDI_HIT_GROUP_TYPE
title: D3D12DDI_HIT_GROUP_TYPE
description: Specifies the type of hit group.
ms.assetid: 034e47d9-920b-4f80-88c9-ec1b305e9e72
ms.date: 10/19/2018
ms.topic: enum
ms.keywords: D3D12DDI_HIT_GROUP_TYPE, D3D12DDI_HIT_GROUP_TYPE, 
req.header: d3d12umddi.h
req.include-header:
req.target-type:
req.target-min-winverclnt: Windows 10, version 1809
req.target-min-winversvr:
req.kmdf-ver:
req.umdf-ver:
req.ddi-compliance:
req.max-support:
req.typenames: D3D12DDI_HIT_GROUP_TYPE
topic_type: 
-	apiref
api_type: 
-	HeaderDef
api_location: 
-	d3d12umddi.h
api_name: 
-	D3D12DDI_HIT_GROUP_TYPE
product:
-	Windows
targetos: Windows
tech.root: display
ms.custom: RS5
---

# D3D12DDI_HIT_GROUP_TYPE enumeration

## -description

Specifies the type of hit group.

## -enum-fields

### -field D3D12DDI_HIT_GROUP_TYPE_TRIANGLES

Hit group type triangles.

### -field D3D12DDI_HIT_GROUP_TYPE_PROCEDURAL_PRIMITIVE 

Hit group type procedural primitive.

## -remarks

A hit group is one or more shaders consisting of:

* 0 or 1 intersection shader
* 0 or 1 any hit shader
* 0 or 1 closest hit shader

## -see-also
