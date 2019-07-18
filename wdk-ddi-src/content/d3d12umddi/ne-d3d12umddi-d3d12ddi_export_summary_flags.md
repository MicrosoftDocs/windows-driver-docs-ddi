---
UID: NE:d3d12umddi.D3D12DDI_EXPORT_SUMMARY_FLAGS
title: D3D12DDI_EXPORT_SUMMARY_FLAGS (d3d12umddi.h)
description: Flags indicating properties the runtime has determined about a given shader export.
ms.assetid: 3b2c93b4-4ec7-4208-8cdc-dba1bda085a9
ms.date: 10/19/2018
ms.topic: enum
f1_keywords:
 - "d3d12umddi/D3D12DDI_EXPORT_SUMMARY_FLAGS"
ms.keywords: D3D12DDI_EXPORT_SUMMARY_FLAGS, D3D12DDI_EXPORT_SUMMARY_FLAGS, 
req.header: d3d12umddi.h
req.include-header:
req.target-type:
req.target-min-winverclnt: Windows 10, version 1809
req.target-min-winversvr:
req.kmdf-ver:
req.umdf-ver:
req.ddi-compliance:
req.max-support:
req.typenames: D3D12DDI_EXPORT_SUMMARY_FLAGS
topic_type: 
- apiref
api_type: 
- HeaderDef
api_location: 
- d3d12umddi.h
api_name: 
- D3D12DDI_EXPORT_SUMMARY_FLAGS
product:
- Windows
targetos: Windows
tech.root: display
ms.custom: RS5
---

# D3D12DDI_EXPORT_SUMMARY_FLAGS enumeration

## -description

Flags indicating properties the runtime has determined about a given shader export, including the graph of functions it may call.  


## -enum-fields

### -field D3D12DDI_EXPORT_SUMMARY_FLAG_NONE

No flag.

### -field D3D12DDI_EXPORT_SUMMARY_FLAG_UNRESOLVED_RESOURCE_BINDINGS

Unresolved resource bindings.

### -field D3D12DDI_EXPORT_SUMMARY_FLAG_UNRESOLVED_FUNCTIONS

Unresolved functions.

### -field D3D12DDI_EXPORT_SUMMARY_FLAG_UNRESOLVED_ASSOCIATIONS

Unresolved associations.

## -remarks

Unresolved resource bindings or unresolved functions can only appear for collection state objects, because the runtime ensures all dependencies are resolved for executable state objects.  

There is still the possibility of the driver finding code incompatibility while linking code across DXIL (DirectX Intermediate Language) libraries that the runtime missed, since the runtime isn’t doing full linking. For instance, a shader in one DXIL library might call a function where a parameter is a user defined type that has been defined locally.  The function being called may appear in a different DXIL library with the same function signature but having the user defined type defined differently there.  Without doing full linking, the runtime could miss this, in which case the driver would have to fail state object creation.

## -see-also
