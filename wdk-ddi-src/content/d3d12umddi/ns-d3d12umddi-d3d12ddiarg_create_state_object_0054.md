---
UID: NS:d3d12umddi.D3D12DDIARG_CREATE_STATE_OBJECT_0054
title: D3D12DDIARG_CREATE_STATE_OBJECT_0054
author: windows-driver-content
description: Arguments used in the CreateStateObject callback function to create a state object.
ms.assetid: 7d270c05-641d-44a4-b688-2c3a1c25bd6d
ms.author: windowsdriverdev
ms.date: 
ms.topic: struct
ms.prod: windows-hardware
ms.technology: windows-devices
ms.keywords: D3D12DDIARG_CREATE_STATE_OBJECT_0054, D3D12DDIARG_CREATE_STATE_OBJECT_0054, 
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
req.typenames: D3D12DDIARG_CREATE_STATE_OBJECT_0054
topic_type: 
-	apiref
api_type: 
-	HeaderDef
api_location: 
-	d3d12umddi.h
api_name: 
-	D3D12DDIARG_CREATE_STATE_OBJECT_0054
product:
-	Windows
targetos: Windows
tech.root: display
---

# D3D12DDIARG_CREATE_STATE_OBJECT_0054 structure

## -description

Arguments used in the [CreateStateObject](nc-d3d12umddi-pfnd3d12ddi_create_state_object_0054.md) callback function to create a state object.

## -struct-fields

### -field Type

The [D3D12DDI_STATE_OBJECT_TYPE](ne-d3d12umddi-d3d12ddi_state_object_type.md) type.

### -field NumSubobjects

The number of [D3D12DDI_STATE_SUBOBJECT_0054](ns-d3d12umddi-d3d12ddi_state_subobject_0054.md) structures in the *pSubobjects* array. 

### -field pSubobjects
 
Pointer to an array of [D3D12DDI_STATE_SUBOBJECT_0054](ns-d3d12umddi-d3d12ddi_state_subobject_0054.md) structures.

## -remarks

## -see-also