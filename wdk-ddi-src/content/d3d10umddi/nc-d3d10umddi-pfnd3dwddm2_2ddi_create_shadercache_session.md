---
UID: NC:d3d10umddi.PFND3DWDDM2_2DDI_CREATE_SHADERCACHE_SESSION
title: PFND3DWDDM2_2DDI_CREATE_SHADERCACHE_SESSION (d3d10umddi.h)
description: The pfnCreateShaderCacheSession callback function creates a shader cache session.
old-location: display\pfnd3dwddm2_2ddi_create_shadercache_session.htm
ms.assetid: 14B3AB7A-DB27-412F-9578-5BA44628ECE7
ms.date: 05/10/2018
keywords: ["PFND3DWDDM2_2DDI_CREATE_SHADERCACHE_SESSION callback function"]
ms.keywords: PFND3DWDDM2_2DDI_CREATE_SHADERCACHE_SESSION, PFND3DWDDM2_2DDI_CREATE_SHADERCACHE_SESSION callback, d3d10umddi/pfnCreateShaderCacheSession, display.pfnd3dwddm2_2ddi_create_shadercache_session, pfnCreateShaderCacheSession, pfnCreateShaderCacheSession callback function [Display Devices]
f1_keywords:
 - "d3d10umddi/pfnCreateShaderCacheSession"
 - "pfnCreateShaderCacheSession"
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
topic_type:
- APIRef
- kbSyntax
api_type:
- UserDefined
api_location:
- d3d10umddi.h
api_name:
- pfnCreateShaderCacheSession
product:
- Windows
targetos: Windows
tech.root: display
req.typenames: 
---

# PFND3DWDDM2_2DDI_CREATE_SHADERCACHE_SESSION callback function


## -description


The <i>pfnCreateShaderCacheSession</i> callback function creates a shader cache session.


## -parameters

### -param Arg1

*hDevice* [in]

The handle of a device.


### -param Arg2

*hCacheSession*

The handle of a cache session.

### -param Arg3

*hRTCacheSession*

The handle of the cache session for the driver to use when it calls back into the runtime.



## -remarks



The runtime uses the object that is created to inform the driver of different caching contexts. It can be used to direct the caching callbacks towards a process-local cache or a per-component cache which is shared by multiple processes.

Access this callback function by using the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/ns-d3d10umddi-d3dwddm2_2ddi_devicefuncs">D3DWDDM2_2DDI_DEVICEFUNCS</a> structure. 




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/ns-d3d10umddi-d3dwddm2_2ddi_devicefuncs">D3DWDDM2_2DDI_DEVICEFUNCS</a>
 

 

