---
UID: NC:d3d10umddi.PFND3DWDDM2_2DDI_SHADERCACHE_STORE_VALUE_CB
title: PFND3DWDDM2_2DDI_SHADERCACHE_STORE_VALUE_CB
author: windows-driver-content
description: The pfnShaderCacheStoreValue callback function stores a shader cache value.
old-location: display\pfnd3dwddm2_2ddi_shadercache_store_value.htm
old-project: display
ms.assetid: 715D4C28-029F-463E-9A6D-D8155B570538
ms.author: windowsdriverdev
ms.date: 4/16/2018
ms.keywords: PFND3DWDDM2_2DDI_SHADERCACHE_STORE_VALUE_CB, PFND3DWDDM2_2DDI_SHADERCACHE_STORE_VALUE_CB callback, d3d12umddi/pfnShaderCacheStoreValue, display.pfnd3dwddm2_2ddi_shadercache_store_value, pfnShaderCacheStoreValue, pfnShaderCacheStoreValue callback function [Display Devices]
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	UserDefined
api_location:
-	D3d12umddi.h
api_name:
-	pfnShaderCacheStoreValue
product:
- Windows
targetos: Windows
req.typenames: 
---

# PFND3DWDDM2_2DDI_SHADERCACHE_STORE_VALUE_CB callback function


## -description


The <i>pfnShaderCacheStoreValue</i> callback function stores a shader cache value.


## -parameters




### -param hCacheSession

The handle of the cache session for the driver to use when it calls back into the runtime.


### -param *pPrecomputedHash [in]

A hash value. 


### -param *pKey [in]

A pointer to a key.


### -param KeyLen

The length of the key.


### -param *pValue [in]

A pointer to an input value. 


### -param ValueLen

The length of the input value.


## -returns



If this callback function succeeds, it returns <b xmlns:loc="http://microsoft.com/wdcml/l10n">S_OK</b>. Otherwise, it returns an <b xmlns:loc="http://microsoft.com/wdcml/l10n">HRESULT</b> error code.



