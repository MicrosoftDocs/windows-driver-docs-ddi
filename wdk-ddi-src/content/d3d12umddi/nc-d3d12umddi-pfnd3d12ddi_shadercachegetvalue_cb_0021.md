---
UID: NC:d3d12umddi.PFND3D12DDI_SHADERCACHEGETVALUE_CB_0021
title: PFND3D12DDI_SHADERCACHEGETVALUE_CB_0021 (d3d12umddi.h)
description: Learn about the pfnShaderCacheGetValueCb callback.
ms.date: 04/23/2024
keywords: ["PFND3D12DDI_SHADERCACHEGETVALUE_CB_0021 callback function"]
ms.keywords: PFND3D12DDI_SHADERCACHEGETVALUE_CB_0021, PFND3D12DDI_SHADERCACHEGETVALUE_CB_0021 callback, d3d12umddi/pfnShaderCacheGetValueCb, display.pfnd3d12ddi_shadercachegetvalue_cb_0021, pfnShaderCacheGetValueCb, pfnShaderCacheGetValueCb callback function [Display Devices]
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
 - PFND3D12DDI_SHADERCACHEGETVALUE_CB_0021
 - d3d12umddi/PFND3D12DDI_SHADERCACHEGETVALUE_CB_0021
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - D3d12umddi.h
api_name:
 - PFND3D12DDI_SHADERCACHEGETVALUE_CB_0021
---

# PFND3D12DDI_SHADERCACHEGETVALUE_CB_0021 callback function

## -description

The **pfnShaderCacheGetValueCb** callback function gets a value stored in the shader cache.

## -parameters

### -param hRTDevice

[in] Handle to the runtime's representation of the device.

### -param hRTPSO

[in] Handle to the runtime's representation of a pipeline state object.

### -param pPrecomputedHash

[in] A [**D3D12DDI_SHADERCACHE_HASH**](ns-d3d12umddi-d3d12ddi_shadercache_hash.md) structure that contains the hash value to use for cache lookup.

### -param pKey

[in] A pointer to the key associated with the value to be retrieved from the driver's shader cache. The key uniquely identifies the shader data in the cache.

### -param KeyLen

[in] The length of the key that **pKey** points to, in bytes.

### -param pValue

[out] A pointer to the compiled shader code or other data associated with the shader identified by **pPrecomputedHash** and **pKey**. This parameter can be NULL if **pValueLen** is zero.

### -param pValueLen

[in/out] Pointer to a variable that specifies the length of the buffer that **pValue** points to, in bytes. On input, this variable specifies the size of the buffer. On output, it specifies the size of the data that was written to the buffer. If **pValueLen** is set to zero and **pValue** is NULL, **pfnShaderCacheGetValueCb** should write the number of bytes needed for the data in a second call to it. Otherwise, if the buffer that **pValue** points to is too small, the function should fail.

## -returns

If this callback function succeeds, it returns **S_OK**. Otherwise, it returns an **HRESULT** error code.

## -remarks

The [**pfnShaderCacheStoreValueCb**](nc-d3d12umddi-pfnd3d12ddi_shadercachestorevalue_cb_0021.md) and **pfnShaderCacheGetValueCb** callbacks are used to store and retrieve compiled shader code or other shader-related data in the driver's shader cache. Caching helps improve performance by reducing the need to recompile shaders that have already been compiled and cached.

Access this callback by using the [**D3D12DDI_SHADERCACHE_CALLBACKS_0021**](ns-d3d12umddi-d3d12ddi_shadercache_callbacks_0021.md) structure.

## -see-also

[**D3D12DDI_SHADERCACHE_CALLBACKS_0021**](ns-d3d12umddi-d3d12ddi_shadercache_callbacks_0021.md)

[**pfnShaderCacheStoreValueCb**](nc-d3d12umddi-pfnd3d12ddi_shadercachestorevalue_cb_0021.md)
