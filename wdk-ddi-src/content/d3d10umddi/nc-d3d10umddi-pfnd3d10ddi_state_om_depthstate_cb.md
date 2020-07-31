---
UID: NC:d3d10umddi.PFND3D10DDI_STATE_OM_DEPTHSTATE_CB
title: PFND3D10DDI_STATE_OM_DEPTHSTATE_CB (d3d10umddi.h)
description: The pfnStateOmDepthStateCb function causes the Microsoft Direct3D 10 runtime to refresh the output merger depth state.
old-location: display\pfnstateomdepthstatecb.htm
ms.assetid: caa8ea5b-7167-444a-9d81-6e4ea9375dd6
ms.date: 05/10/2018
keywords: ["PFND3D10DDI_STATE_OM_DEPTHSTATE_CB callback function"]
ms.keywords: PFND3D10DDI_STATE_OM_DEPTHSTATE_CB, PFND3D10DDI_STATE_OM_DEPTHSTATE_CB callback, d3d10state_functions_85bda608-2aa7-4756-9901-4f568b87ca6b.xml, d3d10umddi/pfnStateOmDepthStateCb, display.pfnstateomdepthstatecb, pfnStateOmDepthStateCb, pfnStateOmDepthStateCb callback function [Display Devices]
f1_keywords:
 - "d3d10umddi/pfnStateOmDepthStateCb"
 - "pfnStateOmDepthStateCb"
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
- pfnStateOmDepthStateCb
targetos: Windows
tech.root: display
req.typenames: 
---

# PFND3D10DDI_STATE_OM_DEPTHSTATE_CB callback function


## -description


The <b>pfnStateOmDepthStateCb</b> function causes the Microsoft Direct3D 10 runtime to refresh the output merger depth state.


## -parameters




### -param Arg1

*hRuntimeDevice* [in]

A handle to a context for the core Direct3D 10 runtime. This handle is supplied to the driver in a call to the driver's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d10ddi_createdevice">CreateDevice(D3D10)</a> function. 


## -remarks



The <b>pfnStateOmDepthStateCb</b> function calls the user-mode display driver's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d10ddi_setdepthstencilstate">SetDepthStencilState</a> function with the current depth stencil state.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d10ddi_createdevice">CreateDevice(D3D10)</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/ns-d3d10umddi-d3d10ddi_corelayer_devicecallbacks">D3D10DDI_CORELAYER_DEVICECALLBACKS</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d10ddi_setdepthstencilstate">SetDepthStencilState</a>
 

 

