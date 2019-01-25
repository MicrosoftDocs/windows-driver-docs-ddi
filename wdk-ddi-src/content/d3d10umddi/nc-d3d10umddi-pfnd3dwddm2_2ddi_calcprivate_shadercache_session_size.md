---
UID: NC:d3d10umddi.PFND3DWDDM2_2DDI_CALCPRIVATE_SHADERCACHE_SESSION_SIZE
title: PFND3DWDDM2_2DDI_CALCPRIVATE_SHADERCACHE_SESSION_SIZE (d3d10umddi.h)
description: The pfnCalcPrivateShaderCacheSessionSize callback function returns the size of a private shader cache session.
old-location: display\pfnd3dwddm2_2ddi_calcprivate_shadercache_session_size.htm
ms.assetid: 86FD1B35-878A-4D68-83CB-7F322CD9006D
ms.date: 05/10/2018
ms.keywords: PFND3DWDDM2_2DDI_CALCPRIVATE_SHADERCACHE_SESSION_SIZE, PFND3DWDDM2_2DDI_CALCPRIVATE_SHADERCACHE_SESSION_SIZE callback, d3d10umddi/pfnCalcPrivateShaderCacheSessionSize, display.pfnd3dwddm2_2ddi_calcprivate_shadercache_session_size, pfnCalcPrivateShaderCacheSessionSize, pfnCalcPrivateShaderCacheSessionSize callback function [Display Devices]
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
-	pfnCalcPrivateShaderCacheSessionSize
product:
- Windows
targetos: Windows
tech.root: display
req.typenames: 
---

# PFND3DWDDM2_2DDI_CALCPRIVATE_SHADERCACHE_SESSION_SIZE callback function


## -description


The <i>pfnCalcPrivateShaderCacheSessionSize</i> callback function returns the size of a private shader cache session.


## -parameters

### -param Arg1

*hDevice*

The handle of a device.

## -returns



This function returns the size of the private shader cache session.




## -remarks



Access this callback function by using the <a href="https://msdn.microsoft.com/4E082193-70BA-4F36-9001-2A12014F3AC3">D3DWDDM2_2DDI_DEVICEFUNCS</a> structure. 




## -see-also




<a href="https://msdn.microsoft.com/4E082193-70BA-4F36-9001-2A12014F3AC3">D3DWDDM2_2DDI_DEVICEFUNCS</a>
 

 

