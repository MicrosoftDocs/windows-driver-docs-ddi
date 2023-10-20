---
UID: NE:d3d12umddi.D3D12DDI_SHADER_MIN_PRECISION
tech.root: display
title: D3D12DDI_SHADER_MIN_PRECISION
ms.date: 10/19/2023
targetos: Windows
description: Learn more about the D3D12DDI_SHADER_MIN_PRECISION enumeration.
prerelease: false
req.construct-type: enumeration
req.ddi-compliance: 
req.header: d3d12umddi.h
req.include-header: 
req.kmdf-ver: 
req.max-support: 
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.target-type: 
req.typenames: 
typedef_isUnnamed: false
req.umdf-ver: 
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - d3d12umddi.h
api_name:
 - D3D12DDI_SHADER_MIN_PRECISION
f1_keywords:
 - D3D12DDI_SHADER_MIN_PRECISION
 - d3d12umddi/D3D12DDI_SHADER_MIN_PRECISION
dev_langs:
 - c++
helpviewer_keywords:
 - D3D12DDI_SHADER_MIN_PRECISION
---

## -description

The **D3D12DDI_SHADER_MIN_PRECISION** enumeration describes the driver's minimum precision support options for shaders.

## -enum-fields

### -field D3D12DDI_SHADER_MIN_PRECISION_NONE:0x0

The driver supports only full 32-bit precision for all shader stages.

### -field D3D12DDI_SHADER_MIN_PRECISION_10_BIT:0x1

The driver supports 10-bit precision.

### -field D3D12DDI_SHADER_MIN_PRECISION_16_BIT:0x2

The driver supports 16-bit precision.

## -remarks

The returned information just indicates that the graphics hardware can perform HLSL operations at a lower precision than the standard 32-bit float precision, but doesn’t guarantee that the graphics hardware will actually run at a lower precision.

## -see-also

[**D3D12DDI_SHADER_CAPS_0084**](ns-d3d12umddi-d3d12ddi_shader_caps_0084.md)
