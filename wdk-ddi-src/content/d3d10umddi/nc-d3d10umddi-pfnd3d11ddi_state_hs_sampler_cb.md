---
UID: NC:d3d10umddi.PFND3D11DDI_STATE_HS_SAMPLER_CB
title: PFND3D11DDI_STATE_HS_SAMPLER_CB
author: windows-driver-content
description: The pfnStateHsSamplerCb function causes the Microsoft Direct3D 11 runtime to refresh the hull shader sample state.
old-location: display\pfnstatehssamplercb.htm
ms.assetid: 95475c7a-874c-45e9-ab92-1c3983315446
ms.author: windowsdriverdev
ms.date: 5/10/2018
ms.keywords: PFND3D11DDI_STATE_HS_SAMPLER_CB, PFND3D11DDI_STATE_HS_SAMPLER_CB callback, d3d10umddi/pfnStateHsSamplerCb, d3d11state_functions_36ac0f95-b5df-45d2-bae7-38c2ea1986b7.xml, display.pfnstatehssamplercb, pfnStateHsSamplerCb, pfnStateHsSamplerCb callback function [Display Devices]
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: d3d10umddi.h
req.include-header: D3d10umddi.h
req.target-type: Desktop
req.target-min-winverclnt: pfnStateHsSamplerCb is supported beginning with the Windows 7 operating system.
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
-	pfnStateHsSamplerCb
product:
- Windows
targetos: Windows
tech.root: display
req.typenames: 
---

# PFND3D11DDI_STATE_HS_SAMPLER_CB callback function


## -description


The <b>pfnStateHsSamplerCb</b> function causes the Microsoft Direct3D 11 runtime to refresh the hull shader sample state. 


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
 

 

