---
UID: NC:d3d12umddi.PFND3D12DDI_IMPLICITSHADERCACHECONTROL_0080
tech.root: display
title: PFND3D12DDI_IMPLICITSHADERCACHECONTROL_0080
ms.date: 05/13/2021
targetos: Windows
description: The pfnImplicitShaderCacheControl callback function can optionally perform an application-requested action on the driver-managed shader cache.
req.assembly: 
req.construct-type: function
req.ddi-compliance: 
req.dll: 
req.header: d3d12umddi.h
req.idl: 
req.include-header: 
req.irql: 
req.kmdf-ver: 
req.lib: 
req.max-support: 
req.namespace: 
req.redist: 
req.target-min-winverclnt: 
req.target-min-winversvr: Windows Server 2022
req.target-type: 
req.type-library: 
req.umdf-ver: 
req.unicode-ansi: 
topic_type:
 - apiref
api_type:
 - LibDef
api_location:
 - d3d12umddi.h
api_name:
 - PFND3D12DDI_IMPLICITSHADERCACHECONTROL_0080
f1_keywords:
 - PFND3D12DDI_IMPLICITSHADERCACHECONTROL_0080
 - d3d12umddi/PFND3D12DDI_IMPLICITSHADERCACHECONTROL_0080
dev_langs:
 - c++
---

## -description

The **pfnImplicitShaderCacheControl** callback function can optionally perform an application-requested action on the driver-managed shader cache.

## -parameters

### -param unnamedParam1

A handle to the display device (graphics context).

### -param unnamedParam2

A [**D3D12DDI_IMPLICIT_SHADER_CACHE_CONTROL_FLAGS_0080**](ne-d3d12umddi-d3d12ddi_implicit_shader_cache_control_flags_0080.md) value that describes the shader cache control action(s) to take on the driver-managed shader cache.

## -remarks

The runtime calls **pfnImplicitShaderCacheControl** in response to an application request for cache control. These application requests are considered as hints to the driver.

This callback function is supported only in developer mode.

See the [D3D12 Shader Cache APIs specification](https://microsoft.github.io/DirectX-Specs/d3d/ShaderCache.html) for more information.

## -see-also

[**D3D12DDI_D3D12_OPTIONS_DATA_008n**](ns-d3d12umddi-d3d12ddi_device_funcs_core_0080.md)

[**D3D12DDI_IMPLICIT_SHADER_CACHE_CONTROL_FLAGS_0080**](ne-d3d12umddi-d3d12ddi_implicit_shader_cache_control_flags_0080.md)
