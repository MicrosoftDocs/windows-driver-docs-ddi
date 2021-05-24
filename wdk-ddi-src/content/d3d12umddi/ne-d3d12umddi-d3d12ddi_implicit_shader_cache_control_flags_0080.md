---
UID: NE:d3d12umddi.D3D12DDI_IMPLICIT_SHADER_CACHE_CONTROL_FLAGS_0080
tech.root: display
title: D3D12DDI_IMPLICIT_SHADER_CACHE_CONTROL_FLAGS_0080
ms.date: 05/13/2021
targetos: Windows
description: D3D12DDI_IMPLICIT_SHADER_CACHE_CONTROL_FLAGS_0080 enumerates the shader cache control action that the driver should take.
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
req.umdf-ver: 
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - d3d12umddi.h
api_name:
 - D3D12DDI_IMPLICIT_SHADER_CACHE_CONTROL_FLAGS_0080
f1_keywords:
 - D3D12DDI_IMPLICIT_SHADER_CACHE_CONTROL_FLAGS_0080
 - d3d12umddi/D3D12DDI_IMPLICIT_SHADER_CACHE_CONTROL_FLAGS_0080
dev_langs:
 - c++
---

## -description

**D3D12DDI_IMPLICIT_SHADER_CACHE_CONTROL_FLAGS_0080** enumerates the control action(s) to take on a driver-managed shader cache.

## -enum-fields

### -field D3D12DDI_IMPLICIT_SHADER_CACHE_CONTROL_FLAG_0080_DISABLE

Disable the shader cache. A disabled cache cannot be used to look up data or have new data stored in it.

### -field D3D12DDI_IMPLICIT_SHADER_CACHE_CONTROL_FLAG_0080_ENABLE

Resumes use of the cache.

### -field D3D12DDI_IMPLICIT_SHADER_CACHE_CONTROL_FLAG_0080_CLEAR

Delete any existing cache content.

## -remarks

**D3D12DDI_IMPLICIT_SHADER_CACHE_CONTROL_FLAGS_0080** is a parameter passed to a driver's [**PFND3D12DDI_IMPLICITSHADERCACHECONTROL_0080**](nc-d3d12umddi-pfnd3d12ddi_implicitshadercachecontrol_0080.md).

A driver will not receive both **D3D12DDI_IMPLICIT_SHADER_CACHE_CONTROL_FLAG_0080_DISABLE** and **D3D12DDI_IMPLICIT_SHADER_CACHE_CONTROL_FLAG_0080_ENABLE** at the same time.

See the [D3D12 Shader Cache APIs specification](https://https://microsoft.github.io/DirectX-Specs/d3d/ShaderCache.html) for more information.

## -see-also

[**PFND3D12DDI_IMPLICITSHADERCACHECONTROL_0080**](nc-d3d12umddi-pfnd3d12ddi_implicitshadercachecontrol_0080.md)
