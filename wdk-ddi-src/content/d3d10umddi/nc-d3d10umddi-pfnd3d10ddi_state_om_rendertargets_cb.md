---
UID: NC:d3d10umddi.PFND3D10DDI_STATE_OM_RENDERTARGETS_CB
title: PFND3D10DDI_STATE_OM_RENDERTARGETS_CB (d3d10umddi.h)
description: The pfnStateOmRenderTargetsCb function causes the Microsoft Direct3D 10 runtime to refresh the output merger's bound render targets.
old-location: display\pfnstateomrendertargetscb.htm
ms.assetid: d17cd31d-44a1-4f7d-82be-1201c0d5769f
ms.date: 05/10/2018
ms.keywords: PFND3D10DDI_STATE_OM_RENDERTARGETS_CB, PFND3D10DDI_STATE_OM_RENDERTARGETS_CB callback, d3d10state_functions_d1d161af-c985-4d8d-b734-7acda03b13ce.xml, d3d10umddi/pfnStateOmRenderTargetsCb, display.pfnstateomrendertargetscb, pfnStateOmRenderTargetsCb, pfnStateOmRenderTargetsCb callback function [Display Devices]
f1_keywords:
 - "d3d10umddi/pfnStateOmRenderTargetsCb"
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
- APIRef
- kbSyntax
api_type:
- UserDefined
api_location:
- d3d10umddi.h
api_name:
- pfnStateOmRenderTargetsCb
product:
- Windows
targetos: Windows
tech.root: display
req.typenames: 
---

# PFND3D10DDI_STATE_OM_RENDERTARGETS_CB callback function


## -description


The <b>pfnStateOmRenderTargetsCb</b> function causes the Microsoft Direct3D 10 runtime to refresh the output merger's bound render targets.


## -parameters




### -param Arg1

*hRuntimeDevice* [in]

A handle to a context for the core Direct3D 10 runtime. This handle is supplied to the driver in a call to the driver's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d10ddi_createdevice">CreateDevice(D3D10)</a> function. 


## -remarks



The <b>pfnStateOmRenderTargetsCb</b> function calls the user-mode display driver's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d10ddi_setrendertargets">SetRenderTargets</a> function with all of the currently set render target surfaces.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d10ddi_createdevice">CreateDevice(D3D10)</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/ns-d3d10umddi-d3d10ddi_corelayer_devicecallbacks">D3D10DDI_CORELAYER_DEVICECALLBACKS</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d10ddi_setrendertargets">SetRenderTargets</a>
 

 

