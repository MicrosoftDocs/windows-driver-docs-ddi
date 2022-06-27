---
UID: NE:d3d12umddi.D3D12DDI_STATE_OBJECT_FLAGS
title: D3D12DDI_STATE_OBJECT_FLAGS (d3d12umddi.h)
description: The state object flags.
ms.date: 05/24/2022
keywords: ["D3D12DDI_STATE_OBJECT_FLAGS enumeration"]
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
targetos: Windows
tech.root: display
ms.custom: RS5
f1_keywords:
 - D3D12DDI_STATE_OBJECT_FLAGS
 - d3d12umddi/D3D12DDI_STATE_OBJECT_FLAGS
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - d3d12umddi.h
api_name:
 - D3D12DDI_STATE_OBJECT_FLAGS
dev_langs:
 - c++
---

# D3D12DDI_STATE_OBJECT_FLAGS enumeration

## -description

**D3D12DDI_STATE_OBJECT_FLAGS** specify constraints for state objects.

## -enum-fields

### -field D3D12DDI_STATE_OBJECT_FLAG_NONE:0x0

There are no state object constraints.

### -field D3D12DDI_STATE_OBJECT_FLAG_ALLOW_LOCAL_DEPENDENCIES_ON_EXTERNAL_DEFINITIONS:0x1

Allows local dependencies on external definitions.

### -field D3D12DDI_STATE_OBJECT_FLAG_ALLOW_EXTERNAL_DEPENDENCIES_ON_LOCAL_DEFINITIONS:0x2

Allows external dependencies on local definitions.

### -field D3D12DDI_STATE_OBJECT_FLAG_ALLOW_STATE_OBJECT_ADDITIONS:0x4

Allows additions to state objects. Available starting with Windows 10, version 2004.

## -remarks

See the [DirectX Raytracing (DXR) functional specification](https://microsoft.github.io/DirectX-Specs/d3d/Raytracing.html) for more information.

## -see-also

[**D3D12_STATE_OBJECT_CONFIG**](ns-d3d12umddi-d3d12ddi_state_object_config_0054.md)

[**PFND3D12DDI_ADD_TO_STATE_OBJECT_0072**](nc-d3d12umddi-pfnd3d12ddi_add_to_state_object_0072.md)
