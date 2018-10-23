---
UID: NC:d3d10umddi.PFND3D11DDI_STATE_DS_SAMPLER_CB
title: PFND3D11DDI_STATE_DS_SAMPLER_CB
author: windows-driver-content
description: The pfnStateDsSamplerCb function causes the Microsoft Direct3D 11 runtime to refresh the domain shader sample state.
old-location: display\pfnstatedssamplercb.htm
ms.assetid: 975da57f-c859-46b0-b98f-400aaf99098d
ms.date: 05/10/2018
ms.keywords: PFND3D11DDI_STATE_DS_SAMPLER_CB, PFND3D11DDI_STATE_DS_SAMPLER_CB callback, d3d10umddi/pfnStateDsSamplerCb, d3d11state_functions_72fa06bf-7878-40ed-9f71-ce857263dc91.xml, display.pfnstatedssamplercb, pfnStateDsSamplerCb, pfnStateDsSamplerCb callback function [Display Devices]
ms.topic: callback
req.header: d3d10umddi.h
req.include-header: D3d10umddi.h
req.target-type: Desktop
req.target-min-winverclnt: pfnStateDsSamplerCb is supported beginning with the Windows 7 operating system.
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
-	pfnStateDsSamplerCb
product:
- Windows
targetos: Windows
tech.root: display
req.typenames: 
---

# PFND3D11DDI_STATE_DS_SAMPLER_CB callback function


## -description


The <b>pfnStateDsSamplerCb</b> function causes the Microsoft Direct3D 11 runtime to refresh the domain shader sample state. 


## -parameters




### -param Arg1

*hRuntimeDevice* [in]

A handle to a context for the core Direct3D runtime. This handle is supplied to the driver in a call to the driver's <a href="https://msdn.microsoft.com/c69eedb1-c975-412c-aa9f-cf64a702f937">CreateDevice(D3D10)</a> function. 


### -param Arg2

Base [in]

The beginning sampler for which the runtime should refresh state. 

### -param Arg3

Count [in]

The total number of samplers. The number can be -1, which specifies that the Direct3D runtime uses its high watermarks to substitute an optimal value (which is typically less than the maximum valid value for <i>Count</i>). However, no non-NULL binding exists in a slot larger than the optimal <i>Count</i> value.



## -returns



None




## -see-also




<a href="https://msdn.microsoft.com/c69eedb1-c975-412c-aa9f-cf64a702f937">CreateDevice(D3D10)</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff542137">D3D11DDI_CORELAYER_DEVICECALLBACKS</a>
 

 

