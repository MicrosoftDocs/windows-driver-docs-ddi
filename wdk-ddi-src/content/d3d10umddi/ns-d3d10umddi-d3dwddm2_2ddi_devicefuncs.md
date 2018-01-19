---
UID: NS:d3d10umddi.D3DWDDM2_2DDI_DEVICEFUNCS
title: D3DWDDM2_2DDI_DEVICEFUNCS
author: windows-driver-content
description: Specifies the callback functions that operate on a shader cache.
old-location: display\d3dwddm2_2ddi_devicefuncs.htm
old-project: display
ms.assetid: 4E082193-70BA-4F36-9001-2A12014F3AC3
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: D3DWDDM2_2DDI_DEVICEFUNCS, D3DWDDM2_2DDI_DEVICEFUNCS
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
req.alt-api: D3DWDDM2_2DDI_DEVICEFUNCS
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
req.typenames: D3DWDDM2_2DDI_DEVICEFUNCS
---

# D3DWDDM2_2DDI_DEVICEFUNCS structure



## -description
Specifies the callback functions that operate on a shader cache. 



## -syntax

````
typedef struct D3DWDDM2_2DDI_DEVICEFUNCS {
  PFND3DWDDM2_2DDI_CALCPRIVATE_SHADERCACHE_SESSION_SIZE pfnCalcPrivateShaderCacheSessionSize;
  PFND3DWDDM2_2DDI_CREATE_SHADERCACHE_SESSION           pfnCreateShaderCacheSession;
  PFND3DWDDM2_2DDI_DESTROY_SHADERCACHE_SESSION          pfnDestroyShaderCacheSession;
  PFND3DWDDM2_2DDI_SET_SHADERCACHE_SESSION              pfnSetShaderCacheSession;
} D3DWDDM2_2DDI_DEVICEFUNCS;
````


## -struct-fields

### -field pfnCalcPrivateShaderCacheSessionSize

A callback function that returns the size of a private shader cache session.


### -field pfnCreateShaderCacheSession

A callback function that creates a shader cache session.


### -field pfnDestroyShaderCacheSession

A callback function that destroys a shader cache session.


### -field pfnSetShaderCacheSession

A callback function that sets a shader cache session.


## -remarks
