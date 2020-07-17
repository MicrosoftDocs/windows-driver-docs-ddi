---
UID: NE:d3d12umddi.D3D12DDI_STATE_OBJECT_FLAGS
title: D3D12DDI_STATE_OBJECT_FLAGS (d3d12umddi.h)
description: The state object flags.
ms.assetid: 6dbef5b3-6e77-46e7-b9d2-20554a3535ff
ms.date: 03/24/2020
keywords: ["D3D12DDI_STATE_OBJECT_FLAGS enumeration"]
f1_keywords:
 - "d3d12umddi/D3D12DDI_STATE_OBJECT_FLAGS"
 - "D3D12DDI_STATE_OBJECT_FLAGS"
ms.keywords: D3D12DDI_STATE_OBJECT_FLAGS, D3D12DDI_STATE_OBJECT_FLAGS, 
req.header: d3d12umddi.h
req.include-header:
req.target-type:
req.target-min-winverclnt: Windows 10, version 1809
req.target-min-winversvr:
req.kmdf-ver:
req.umdf-ver:
req.ddi-compliance:
req.max-support:
req.typenames: D3D12DDI_STATE_OBJECT_FLAGS
topic_type: 
- apiref
api_type: 
- HeaderDef
api_location: 
- d3d12umddi.h
api_name: 
- D3D12DDI_STATE_OBJECT_FLAGS
product:
- Windows
targetos: Windows
tech.root: display
dev_langs:
 - c++
ms.custom: RS5
---

# D3D12DDI_STATE_OBJECT_FLAGS enumeration

## -description

The state object flags.

## -enum-fields

### -field D3D12DDI_STATE_OBJECT_FLAG_NONE

No flag.

### -field D3D12DDI_STATE_OBJECT_FLAG_ALLOW_LOCAL_DEPENDENCIES_ON_EXTERNAL_DEFINITIONS

Allows local dependencies on external definitions.

### -field D3D12DDI_STATE_OBJECT_FLAG_ALLOW_EXTERNAL_DEPENDENCIES_ON_LOCAL_DEFINITIONS

Allows external dependencies on local definitions.

### -field D3D12_STATE_OBJECT_FLAG_ALLOW_STATE_OBJECT_ADDITIONS

Allows additions to state objects. Available starting with Windows 10, version 2004.

## -remarks

See the [DirectX Raytracing (DXR) functional specification](https://microsoft.github.io/DirectX-Specs/d3d/Raytracing.html) for more information.

## -see-also

[**D3D12_STATE_OBJECT_CONFIG**](ns-d3d12umddi-d3d12ddi_state_object_config_0054.md)

[**PFND3D12DDI_ADD_TO_STATE_OBJECT_0072**](nc-d3d12umddi-pfnd3d12ddi_add_to_state_object_0072.md)
