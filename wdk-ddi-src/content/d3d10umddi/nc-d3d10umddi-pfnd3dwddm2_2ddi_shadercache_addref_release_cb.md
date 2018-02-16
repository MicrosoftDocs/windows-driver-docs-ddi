---
UID: NC:d3d10umddi.PFND3DWDDM2_2DDI_SHADERCACHE_ADDREF_RELEASE_CB
title: PFND3DWDDM2_2DDI_SHADERCACHE_ADDREF_RELEASE_CB
author: windows-driver-content
description: The pfnShaderCacheAddRefCb callback function supports the ability to extend the lifetime of a shader cache.
old-location: display\pfnd3dwddm2_2ddi_shadercache_addref_release_cb.htm
old-project: display
ms.assetid: 2CE40805-D530-47EF-B251-DB3878208504
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: display.pfnd3dwddm2_2ddi_shadercache_addref_release_cb, pfnShaderCacheAddRefCb callback function [Display Devices], pfnShaderCacheAddRefCb, PFND3DWDDM2_2DDI_SHADERCACHE_ADDREF_RELEASE_CB, PFND3DWDDM2_2DDI_SHADERCACHE_ADDREF_RELEASE_CB, d3d10umddi/pfnShaderCacheAddRefCb
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	UserDefined
apilocation:
-	d3d10umddi.h
apiname:
-	pfnShaderCacheAddRefCb
product: Windows
targetos: Windows
req.typenames: "*PSETRESULT_INFO, SETRESULT_INFO"
---

# PFND3DWDDM2_2DDI_SHADERCACHE_ADDREF_RELEASE_CB callback


## -description


The <i>pfnShaderCacheAddRefCb</i> callback function supports the ability to extend the lifetime of a shader cache.


## -prototype


````
PFND3DWDDM2_2DDI_SHADERCACHE_ADDREF_RELEASE_CB pfnShaderCacheAddRefCb;

VOID APIENTRY CALLBACK * pfnShaderCacheAddRefCb(
  _In_ D3DWDDM2_2DDI_HRTCACHESESSION hCacheSession
)
{ ... }
````


## -parameters




### -param hCacheSession [in]

The handler of a cache session.


## -returns



This callback function does not return a value.




## -remarks



Access this callback function by using the <a href="..\d3d10umddi\ns-d3d10umddi-d3dwddm2_2ddi_corelayer_devicecallbacks.md">D3DWDDM2_2DDI_CORELAYER_DEVICECALLBACKS</a> structure.




## -see-also

<a href="..\d3d10umddi\ns-d3d10umddi-d3dwddm2_2ddi_corelayer_devicecallbacks.md">D3DWDDM2_2DDI_CORELAYER_DEVICECALLBACKS</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20PFND3DWDDM2_2DDI_SHADERCACHE_ADDREF_RELEASE_CB callback function%20 RELEASE:%20(12/29/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

