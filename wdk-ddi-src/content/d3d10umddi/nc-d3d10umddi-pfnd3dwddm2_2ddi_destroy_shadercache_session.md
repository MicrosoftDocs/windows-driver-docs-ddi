---
UID: NC:d3d10umddi.PFND3DWDDM2_2DDI_DESTROY_SHADERCACHE_SESSION
title: PFND3DWDDM2_2DDI_DESTROY_SHADERCACHE_SESSION
author: windows-driver-content
description: The pfnDestroyShaderCacheSession callback function destroys a shader cache session.
old-location: display\pfnd3dwddm2_2ddi_destroy_shadercache_session.htm
old-project: display
ms.assetid: 1C6AFC89-F740-4309-9389-BFB5C62FCA77
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: PFND3DWDDM2_2DDI_DESTROY_SHADERCACHE_SESSION, d3d10umddi/pfnDestroyShaderCacheSession, display.pfnd3dwddm2_2ddi_destroy_shadercache_session, pfnDestroyShaderCacheSession, pfnDestroyShaderCacheSession callback function [Display Devices]
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
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
-	APIRef
-	kbSyntax
api_type:
-	UserDefined
api_location:
-	d3d10umddi.h
api_name:
-	pfnDestroyShaderCacheSession
product: Windows
targetos: Windows
req.typenames: SETRESULT_INFO, *PSETRESULT_INFO
---

# PFND3DWDDM2_2DDI_DESTROY_SHADERCACHE_SESSION callback


## -description


The <i>pfnDestroyShaderCacheSession</i> callback function destroys a shader cache session.


## -parameters




### -param Arg1


### -param Arg2








#### - hCacheSession

The handle of a cache session.


#### - hDevice

The handle of a device.


## -returns



This callback function does not return a value.




## -remarks



Access this callback function by using the <a href="https://msdn.microsoft.com/4E082193-70BA-4F36-9001-2A12014F3AC3">D3DWDDM2_2DDI_DEVICEFUNCS</a> structure. 




## -see-also




<a href="https://msdn.microsoft.com/4E082193-70BA-4F36-9001-2A12014F3AC3">D3DWDDM2_2DDI_DEVICEFUNCS</a>
 

 

