---
UID: NC:d3d10umddi.PFND3D11DDI_STATE_DS_SAMPLER_CB
title: PFND3D11DDI_STATE_DS_SAMPLER_CB
author: windows-driver-content
description: The pfnStateDsSamplerCb function causes the Microsoft Direct3D 11 runtime to refresh the domain shader sample state.
old-location: display\pfnstatedssamplercb.htm
old-project: display
ms.assetid: 975da57f-c859-46b0-b98f-400aaf99098d
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: PFND3D11DDI_STATE_DS_SAMPLER_CB, d3d10umddi/pfnStateDsSamplerCb, d3d11state_functions_72fa06bf-7878-40ed-9f71-ce857263dc91.xml, display.pfnstatedssamplercb, pfnStateDsSamplerCb, pfnStateDsSamplerCb callback function [Display Devices]
ms.prod: windows-hardware
ms.technology: windows-devices
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
product: Windows
targetos: Windows
req.typenames: SETRESULT_INFO, *PSETRESULT_INFO
---

# PFND3D11DDI_STATE_DS_SAMPLER_CB callback


## -description


The <b>pfnStateDsSamplerCb</b> function causes the Microsoft Direct3D 11 runtime to refresh the domain shader sample state. 


## -prototype


````
PFND3D11DDI_STATE_DS_SAMPLER_CB pfnStateDsSamplerCb;

void APIENTRY pfnStateDsSamplerCb(
  _In_ D3D10DDI_HRTCORELAYER hRuntimeDevice,
  _In_ UINT                  Base,
  _In_ UINT                  Count
)
{ ... }
````


## -parameters




### -param D3D10DDI_HRTCORELAYER


### -param UINT








#### - Base [in]

 The beginning sampler for which the runtime should refresh state. 


#### - Count [in]

 The total number of samplers. The number can be -1, which specifies that the Direct3D runtime uses its high watermarks to substitute an optimal value (which is typically less than the maximum valid value for <i>Count</i>). However, no non-NULL binding exists in a slot larger than the optimal <i>Count</i> value.


#### - hRuntimeDevice [in]

 A handle to a context for the core Direct3D runtime. This handle is supplied to the driver in a call to the driver's <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi_createdevice.md">CreateDevice(D3D10)</a> function. 


## -returns



None




## -see-also

<a href="..\d3d10umddi\ns-d3d10umddi-d3d11ddi_corelayer_devicecallbacks.md">D3D11DDI_CORELAYER_DEVICECALLBACKS</a>



<a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi_createdevice.md">CreateDevice(D3D10)</a>



 

 


