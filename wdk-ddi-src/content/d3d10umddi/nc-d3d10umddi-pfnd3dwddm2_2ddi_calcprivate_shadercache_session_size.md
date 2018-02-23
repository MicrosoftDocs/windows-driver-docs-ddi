---
UID: NC:d3d10umddi.PFND3DWDDM2_2DDI_CALCPRIVATE_SHADERCACHE_SESSION_SIZE
title: PFND3DWDDM2_2DDI_CALCPRIVATE_SHADERCACHE_SESSION_SIZE
author: windows-driver-content
description: The pfnCalcPrivateShaderCacheSessionSize callback function returns the size of a private shader cache session.
old-location: display\pfnd3dwddm2_2ddi_calcprivate_shadercache_session_size.htm
old-project: display
ms.assetid: 86FD1B35-878A-4D68-83CB-7F322CD9006D
ms.author: windowsdriverdev
ms.date: 2/22/2018
ms.keywords: display.pfnd3dwddm2_2ddi_calcprivate_shadercache_session_size, pfnCalcPrivateShaderCacheSessionSize callback function [Display Devices], pfnCalcPrivateShaderCacheSessionSize, PFND3DWDDM2_2DDI_CALCPRIVATE_SHADERCACHE_SESSION_SIZE, PFND3DWDDM2_2DDI_CALCPRIVATE_SHADERCACHE_SESSION_SIZE, d3d10umddi/pfnCalcPrivateShaderCacheSessionSize
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
-	pfnCalcPrivateShaderCacheSessionSize
product: Windows
targetos: Windows
req.typenames: SETRESULT_INFO, *PSETRESULT_INFO
---

# PFND3DWDDM2_2DDI_CALCPRIVATE_SHADERCACHE_SESSION_SIZE callback


## -description


The <i>pfnCalcPrivateShaderCacheSessionSize</i> callback function returns the size of a private shader cache session.


## -prototype


````
PFND3DWDDM2_2DDI_CALCPRIVATE_SHADERCACHE_SESSION_SIZE pfnCalcPrivateShaderCacheSessionSize;

SIZE_T APIENTRY* pfnCalcPrivateShaderCacheSessionSize(
   D3D10DDI_HDEVICE hDevice
)
{ ... }
````


## -parameters




### -param D3D10DDI_HDEVICE








#### - hDevice

The handle of a device.


## -returns



This function returns the size of the private shader cache session.




## -remarks



Access this callback function by using the <a href="..\d3d10umddi\ns-d3d10umddi-d3dwddm2_2ddi_devicefuncs.md">D3DWDDM2_2DDI_DEVICEFUNCS</a> structure. 




## -see-also

<a href="..\d3d10umddi\ns-d3d10umddi-d3dwddm2_2ddi_devicefuncs.md">D3DWDDM2_2DDI_DEVICEFUNCS</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20PFND3DWDDM2_2DDI_CALCPRIVATE_SHADERCACHE_SESSION_SIZE callback function%20 RELEASE:%20(2/22/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

