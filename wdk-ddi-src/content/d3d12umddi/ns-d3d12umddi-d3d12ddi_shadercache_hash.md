---
UID: NS:d3d12umddi.D3D12DDI_SHADERCACHE_HASH
title: D3D12DDI_SHADERCACHE_HASH (d3d12umddi.h)
description: Learn about the D3D12DDI_SHADERCACHE_HASH structure.
ms.date: 06/27/2024
keywords: ["D3D12DDI_SHADERCACHE_HASH structure"]
ms.keywords: D3D12DDI_SHADERCACHE_HASH, D3D12DDI_SHADERCACHE_HASH structure [Display Devices], d3d12umddi/D3D12DDI_SHADERCACHE_HASH, display.d3d12ddi_shadercache_hash
req.header: d3d12umddi.h
req.include-header: D3d12umddi.h
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: 
targetos: Windows
tech.root: display
req.typenames: D3D12DDI_SHADERCACHE_HASH
f1_keywords:
 - D3D12DDI_SHADERCACHE_HASH
 - d3d12umddi/D3D12DDI_SHADERCACHE_HASH
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - D3d12umddi.h
api_name:
 - D3D12DDI_SHADERCACHE_HASH
---

# D3D12DDI_SHADERCACHE_HASH structure

## -description

The **D3D12DDI_SHADERCACHE_HASH** structure contains a hash value associated with a shader in the shader cache.

## -struct-fields

### -field Hash

A hash value. When a shader is compiled, a hash value based on the shader code and possibly other relevant data is computed. This hash is then used as a key to store and retrieve the compiled shader code from the shader cache.

## -see-also

[**PFND3D12DDI_CREATE_SHADER_0026**](nc-d3d12umddi-pfnd3d12ddi_create_shader_0026.md)

[**pfnShaderCacheGetValueCb**](nc-d3d12umddi-pfnd3d12ddi_shadercachegetvalue_cb_0021.md)

[**pfnShaderCacheStoreValueCb**](nc-d3d12umddi-pfnd3d12ddi_shadercachestorevalue_cb_0021.md)
