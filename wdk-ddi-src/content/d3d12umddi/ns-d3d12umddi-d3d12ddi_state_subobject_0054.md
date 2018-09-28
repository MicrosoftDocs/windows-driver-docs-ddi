---
UID: NS:d3d12umddi.D3D12DDI_STATE_SUBOBJECT_0054
title: D3D12DDI_STATE_SUBOBJECT_0054
author: windows-driver-content
description: 
ms.assetid: 01c6b23e-b6cc-40b2-8527-f1abcdbd7a42
ms.author: windowsdriverdev
ms.date: 
ms.topic: struct
ms.prod: windows-hardware
ms.technology: windows-devices
ms.keywords: D3D12DDI_STATE_SUBOBJECT_0054, D3D12DDI_STATE_SUBOBJECT_0054, 
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
req.typenames: D3D12DDI_STATE_SUBOBJECT_0054
topic_type: 
-	apiref
api_type: 
-	HeaderDef
api_location: 
-	d3d12umddi.h
api_name: 
-	D3D12DDI_STATE_SUBOBJECT_0054
product:
-	Windows
targetos: Windows
tech.root: display
---

# D3D12DDI_STATE_SUBOBJECT_0054 structure

## -description

State objects are built out of subobjects. A subobject has a type and corresponding data.

## -struct-fields

### -field Type

A [D3D12DDI_STATE_SUBOBJECT_TYPE](ne-d3d12umddi-d3d12ddi_state_subobject_type.md) that represents the subobject type.

### -field pDesc

Pointer to the description, depending on *Type*.

## -remarks

## -see-also