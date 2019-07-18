---
UID: NC:d3d10umddi.PFND3D11DDI_STATE_DS_SHADER_CB
title: PFND3D11DDI_STATE_DS_SHADER_CB (d3d10umddi.h)
description: The pfnStateDsShaderCb function causes the Microsoft Direct3D 11 runtime to refresh the domain shader.
old-location: display\pfnstatedsshadercb.htm
ms.assetid: 3b50f462-667e-4772-89bb-32d01e1bb7fc
ms.date: 05/10/2018
ms.keywords: PFND3D11DDI_STATE_DS_SHADER_CB, PFND3D11DDI_STATE_DS_SHADER_CB callback, d3d10umddi/pfnStateDsShaderCb, d3d11state_functions_5ab17831-b238-4b96-89bf-84c658463597.xml, display.pfnstatedsshadercb, pfnStateDsShaderCb, pfnStateDsShaderCb callback function [Display Devices]
ms.topic: callback
f1_keywords:
 - "d3d10umddi/pfnStateDsShaderCb"
req.header: d3d10umddi.h
req.include-header: D3d10umddi.h
req.target-type: Desktop
req.target-min-winverclnt: pfnStateDsShaderCb is supported beginning with the Windows 7 operating system.
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
- pfnStateDsShaderCb
product:
- Windows
targetos: Windows
tech.root: display
req.typenames: 
---

# PFND3D11DDI_STATE_DS_SHADER_CB callback function


## -description


The <b>pfnStateDsShaderCb</b> function causes the Microsoft Direct3D 11 runtime to refresh the domain shader.


## -parameters




### -param Arg1

*hRuntimeDevice* [in]

A handle to a context for the core Direct3D runtime. This handle is supplied to the driver in a call to the driver's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3d10umddi/nc-d3d10umddi-pfnd3d10ddi_createdevice">CreateDevice(D3D10)</a> function. 


## -returns



None




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3d10umddi/nc-d3d10umddi-pfnd3d10ddi_createdevice">CreateDevice(D3D10)</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3d10umddi/ns-d3d10umddi-d3d11ddi_corelayer_devicecallbacks">D3D11DDI_CORELAYER_DEVICECALLBACKS</a>
 

 

