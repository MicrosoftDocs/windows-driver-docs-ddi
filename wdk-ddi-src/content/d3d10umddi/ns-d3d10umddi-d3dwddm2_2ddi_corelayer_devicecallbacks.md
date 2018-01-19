---
UID: NS:d3d10umddi.D3DWDDM2_2DDI_CORELAYER_DEVICECALLBACKS
title: D3DWDDM2_2DDI_CORELAYER_DEVICECALLBACKS
author: windows-driver-content
description: Specifies core layer device callback functions.
old-location: display\d3dwddm2_2ddi_corelayer_devicecallbacks.htm
old-project: display
ms.assetid: B42DA194-690F-41A6-AC11-71224887A2E4
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: D3DWDDM2_2DDI_CORELAYER_DEVICECALLBACKS, D3DWDDM2_2DDI_CORELAYER_DEVICECALLBACKS
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: d3d10umddi.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: D3DWDDM2_2DDI_CORELAYER_DEVICECALLBACKS
req.alt-loc: d3d10umddi.h
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
req.typenames: D3DWDDM2_2DDI_CORELAYER_DEVICECALLBACKS
---

# D3DWDDM2_2DDI_CORELAYER_DEVICECALLBACKS structure



## -description
Specifies core layer device callback functions. 



## -syntax

````
typedef struct D3DWDDM2_2DDI_CORELAYER_DEVICECALLBACKS {
  PFND3DWDDM2_2DDI_SHADERCACHE_GET_VALUE         pfnShaderCacheGetValue;
  PFND3DWDDM2_2DDI_SHADERCACHE_STORE_VALUE       pfnShaderCacheStoreValue;
  PFND3DWDDM2_2DDI_SHADERCACHE_ADDREF_RELEASE_CB pfnShaderCacheAddRefCb;
  PFND3DWDDM2_2DDI_SHADERCACHE_ADDREF_RELEASE_CB pfnShaderCacheReleaseCb;
} D3DWDDM2_2DDI_CORELAYER_DEVICECALLBACKS;
````


## -struct-fields

### -field pfnShaderCacheGetValue

A callback function that gets the shader cache value.


### -field pfnShaderCacheStoreValue

A callback function that stores the shader cache value. 


### -field pfnShaderCacheAddRefCb

A callback function that adds a reference to the shader cache. 


### -field pfnShaderCacheReleaseCb

A callback function that releases a reference to a cache. 


## -remarks
