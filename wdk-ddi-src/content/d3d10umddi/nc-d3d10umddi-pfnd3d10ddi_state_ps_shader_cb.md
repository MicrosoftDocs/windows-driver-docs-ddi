---
UID: NC:d3d10umddi.PFND3D10DDI_STATE_PS_SHADER_CB
title: PFND3D10DDI_STATE_PS_SHADER_CB
author: windows-driver-content
description: The pfnStatePsShaderCb function causes the Microsoft Direct3D 10 runtime to refresh the pixel shader stage's shader program.
old-location: display\pfnstatepsshadercb.htm
old-project: display
ms.assetid: 0865e79e-7df9-4dc7-a655-4fbd0af72030
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: PFND3D10DDI_STATE_PS_SHADER_CB, d3d10state_functions_f0180480-dc5e-4d36-8db7-4f32e9e09fc7.xml, d3d10umddi/pfnStatePsShaderCb, display.pfnstatepsshadercb, pfnStatePsShaderCb, pfnStatePsShaderCb callback function [Display Devices]
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
-	pfnStatePsShaderCb
product: Windows
targetos: Windows
req.typenames: SETRESULT_INFO, *PSETRESULT_INFO
---

# PFND3D10DDI_STATE_PS_SHADER_CB callback


## -description


The <b>pfnStatePsShaderCb</b> function causes the Microsoft Direct3D 10 runtime to refresh the pixel shader stage's shader program.


## -parameters




### -param Arg1








#### - hRuntimeDevice [in]

 A handle to a context for the core Direct3D 10 runtime. This handle is supplied to the driver in a call to the driver's <a href="https://msdn.microsoft.com/c69eedb1-c975-412c-aa9f-cf64a702f937">CreateDevice(D3D10)</a> function. 


## -returns



None




## -see-also




<a href="https://msdn.microsoft.com/c69eedb1-c975-412c-aa9f-cf64a702f937">CreateDevice(D3D10)</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff541820">D3D10DDI_CORELAYER_DEVICECALLBACKS</a>
 

 

