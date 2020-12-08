---
UID: NC:d3d10umddi.PFND3DWDDM2_2DDI_SHADERCACHE_STORE_VALUE_CB
title: PFND3DWDDM2_2DDI_SHADERCACHE_STORE_VALUE_CB (d3d10umddi.h)
description: The pfnShaderCacheStoreValue callback function stores a shader cache value.
old-location: display\pfnd3dwddm2_2ddi_shadercache_store_value.htm
ms.date: 05/10/2018
keywords: ["PFND3DWDDM2_2DDI_SHADERCACHE_STORE_VALUE_CB callback function"]
ms.keywords: PFND3DWDDM2_2DDI_SHADERCACHE_STORE_VALUE_CB, PFND3DWDDM2_2DDI_SHADERCACHE_STORE_VALUE_CB callback, d3d12umddi/pfnShaderCacheStoreValue, display.pfnd3dwddm2_2ddi_shadercache_store_value, pfnShaderCacheStoreValue, pfnShaderCacheStoreValue callback function [Display Devices]
req.header: d3d10umddi.h
req.include-header: D3d10umddi.h
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
 - PFND3DWDDM2_2DDI_SHADERCACHE_STORE_VALUE_CB
 - d3d10umddi/PFND3DWDDM2_2DDI_SHADERCACHE_STORE_VALUE_CB
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - D3d12umddi.h
api_name:
 - pfnShaderCacheStoreValue
product:
 - Windows
---

# PFND3DWDDM2_2DDI_SHADERCACHE_STORE_VALUE_CB callback function


## -description

The <i>pfnShaderCacheStoreValue</i> callback function stores a shader cache value.

## -parameters

### -param hCacheSession

The handle of the cache session for the driver to use when it calls back into the runtime.

### -param pPrecomputedHash

A hash value.

### -param pKey

A pointer to a key.

### -param KeyLen

The length of the key.

### -param pValue

A pointer to an input value.

### -param ValueLen

The length of the input value.

## -returns

If this callback function succeeds, it returns **S_OK**. Otherwise, it returns an **HRESULT** error code.

