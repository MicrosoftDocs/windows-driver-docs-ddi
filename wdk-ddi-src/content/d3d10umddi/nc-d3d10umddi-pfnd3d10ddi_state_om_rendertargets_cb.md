---
UID: NC:d3d10umddi.PFND3D10DDI_STATE_OM_RENDERTARGETS_CB
title: PFND3D10DDI_STATE_OM_RENDERTARGETS_CB
author: windows-driver-content
description: The pfnStateOmRenderTargetsCb function causes the Microsoft Direct3D 10 runtime to refresh the output merger's bound render targets.
old-location: display\pfnstateomrendertargetscb.htm
old-project: display
ms.assetid: d17cd31d-44a1-4f7d-82be-1201c0d5769f
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: PFND3D10DDI_STATE_OM_RENDERTARGETS_CB, d3d10state_functions_d1d161af-c985-4d8d-b734-7acda03b13ce.xml, d3d10umddi/pfnStateOmRenderTargetsCb, display.pfnstateomrendertargetscb, pfnStateOmRenderTargetsCb, pfnStateOmRenderTargetsCb callback function [Display Devices]
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: d3d10umddi.h
req.include-header: D3d10umddi.h
req.target-type: Desktop
req.target-min-winverclnt: Available in Windows Vista and later versions of the Windows operating systems.
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
-	pfnStateOmRenderTargetsCb
product: Windows
targetos: Windows
req.typenames: SETRESULT_INFO, *PSETRESULT_INFO
---

# PFND3D10DDI_STATE_OM_RENDERTARGETS_CB callback


## -description


The <b>pfnStateOmRenderTargetsCb</b> function causes the Microsoft Direct3D 10 runtime to refresh the output merger's bound render targets.


## -parameters




### -param Arg1








#### - hRuntimeDevice [in]

 A handle to a context for the core Direct3D 10 runtime. This handle is supplied to the driver in a call to the driver's <a href="https://msdn.microsoft.com/c69eedb1-c975-412c-aa9f-cf64a702f937">CreateDevice(D3D10)</a> function. 


## -returns



None




## -remarks



The <b>pfnStateOmRenderTargetsCb</b> function calls the user-mode display driver's <a href="https://msdn.microsoft.com/852893e6-1f1c-470a-ab72-f52c1e06e0c0">SetRenderTargets</a> function with all of the currently set render target surfaces.




## -see-also




<a href="https://msdn.microsoft.com/c69eedb1-c975-412c-aa9f-cf64a702f937">CreateDevice(D3D10)</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff541820">D3D10DDI_CORELAYER_DEVICECALLBACKS</a>



<a href="https://msdn.microsoft.com/852893e6-1f1c-470a-ab72-f52c1e06e0c0">SetRenderTargets</a>
 

 

