---
UID: NC:d3d10umddi.PFND3DWDDM2_2DDI_SHADERCACHE_ADDREF_RELEASE_CB
title: PFND3DWDDM2_2DDI_SHADERCACHE_ADDREF_RELEASE_CB (d3d10umddi.h)
description: The pfnShaderCacheAddRefCb callback function supports the ability to extend the lifetime of a shader cache.
old-location: display\pfnd3dwddm2_2ddi_shadercache_addref_release_cb.htm
ms.assetid: 2CE40805-D530-47EF-B251-DB3878208504
ms.date: 05/10/2018
keywords: ["PFND3DWDDM2_2DDI_SHADERCACHE_ADDREF_RELEASE_CB callback function"]
ms.keywords: PFND3DWDDM2_2DDI_SHADERCACHE_ADDREF_RELEASE_CB, PFND3DWDDM2_2DDI_SHADERCACHE_ADDREF_RELEASE_CB callback, d3d10umddi/pfnShaderCacheAddRefCb, display.pfnd3dwddm2_2ddi_shadercache_addref_release_cb, pfnShaderCacheAddRefCb, pfnShaderCacheAddRefCb callback function [Display Devices]
req.header: d3d10umddi.h
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
 - "d3d10umddi/pfnShaderCacheAddRefCb"
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - d3d10umddi.h
api_name:
 - pfnShaderCacheAddRefCb
product:
 - Windows
---

# PFND3DWDDM2_2DDI_SHADERCACHE_ADDREF_RELEASE_CB callback function

## -description

The <i>pfnShaderCacheAddRefCb</i> callback function supports the ability to extend the lifetime of a shader cache.

## -parameters

### -param hCacheSession

The handler of a cache session.

## -remarks

Access this callback function by using the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/ns-d3d10umddi-d3dwddm2_2ddi_corelayer_devicecallbacks">D3DWDDM2_2DDI_CORELAYER_DEVICECALLBACKS</a> structure.

## -see-also

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/ns-d3d10umddi-d3dwddm2_2ddi_corelayer_devicecallbacks">D3DWDDM2_2DDI_CORELAYER_DEVICECALLBACKS</a>

