---
UID: NC:d3d12umddi.PFND3D12DDI_SHADERCACHESTOREVALUE_CB_0021
title: PFND3D12DDI_SHADERCACHESTOREVALUE_CB_0021 (d3d12umddi.h)
description: Learn about the pfnShaderCacheStoreValueCb callback.
ms.date: 04/23/2024
keywords: ["PFND3D12DDI_SHADERCACHESTOREVALUE_CB_0021 callback function"]
ms.keywords: PFND3D12DDI_SHADERCACHESTOREVALUE_CB_0021, PFND3D12DDI_SHADERCACHESTOREVALUE_CB_0021 callback, d3d12umddi/pfnShaderCacheStoreValueCb, display.pfnd3d12ddi_shadercachestorevalue_cb_0021, pfnShaderCacheStoreValueCb, pfnShaderCacheStoreValueCb callback function [Display Devices]
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
req.typenames: 
f1_keywords:
 - PFND3D12DDI_SHADERCACHESTOREVALUE_CB_0021
 - d3d12umddi/PFND3D12DDI_SHADERCACHESTOREVALUE_CB_0021
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - D3d12umddi.h
api_name:
 - PFND3D12DDI_SHADERCACHESTOREVALUE_CB_0021
---

# PFND3D12DDI_SHADERCACHESTOREVALUE_CB_0021 callback function

## -description

The **pfnShaderCacheStoreValueCb** callback function stores a value in the shader cache.

## -parameters

### -param hRTDevice

[in] Handle to the runtime's representation of the device.

### -param hRTPSO

[in] Handle to the runtime's representation of a pipeline state object.

### -param pPrecomputedHash

[in] Pointer to a [**D3D12DDI_SHADERCACHE_HASH**](ns-d3d12umddi-d3d12ddi_shadercache_hash.md) structure that contains a precomputed hash value used for cache insertion.

### -param pKey

[in] A pointer to the key associated with the value to be stored in the driver's shader cache. The key uniquely identifies the shader data in the cache.

### -param KeyLen

[in] The length of the key that **pKey** points to, in bytes.

### -param pValue

[in] A pointer to the data to be stored in the shader cache.

### -param ValueLen

[in] The length of the buffer that **pValue** points to, in bytes.

## -returns

If this callback function succeeds, it returns **S_OK**. Otherwise, it returns an **HRESULT** error code.

## -remarks

The **pfnShaderCacheStoreValueCb** and [**pfnShaderCacheGetValueCb**](nc-d3d12umddi-pfnd3d12ddi_shadercachegetvalue_cb_0021.md) callbacks are used to store and retrieve compiled shader code or other shader-related data in the driver's shader cache. Caching helps improve performance by reducing the need to recompile shaders that have already been compiled and cached.

Access this callback by using the [**D3D12DDI_SHADERCACHE_CALLBACKS_0021**](ns-d3d12umddi-d3d12ddi_shadercache_callbacks_0021.md) structure.

## -see-also

[**D3D12DDI_SHADERCACHE_CALLBACKS_0021**](ns-d3d12umddi-d3d12ddi_shadercache_callbacks_0021.md)

[**pfnShaderCacheGetValueCb**](nc-d3d12umddi-pfnd3d12ddi_shadercachegetvalue_cb_0021.md)
