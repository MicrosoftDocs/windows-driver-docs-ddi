---
UID: NC:d3d10umddi.PFND3D10DDI_STATE_VS_SAMPLER_CB
title: PFND3D10DDI_STATE_VS_SAMPLER_CB (d3d10umddi.h)
description: The pfnStateVsSamplerCb function causes the Microsoft Direct3D 10 runtime to refresh the vertex shader stage's bound samplers.
old-location: display\pfnstatevssamplercb.htm
ms.assetid: 5f5dd2ee-72fb-450c-850a-f5546401cd96
ms.date: 05/10/2018
ms.keywords: PFND3D10DDI_STATE_VS_SAMPLER_CB, PFND3D10DDI_STATE_VS_SAMPLER_CB callback, d3d10state_functions_9573517c-75c9-4923-93a8-15ee5b5c4d70.xml, d3d10umddi/pfnStateVsSamplerCb, display.pfnstatevssamplercb, pfnStateVsSamplerCb, pfnStateVsSamplerCb callback function [Display Devices]
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
- APIRef
- kbSyntax
api_type:
- UserDefined
api_location:
- d3d10umddi.h
api_name:
- pfnStateVsSamplerCb
product:
- Windows
targetos: Windows
tech.root: display
req.typenames: 
---

# PFND3D10DDI_STATE_VS_SAMPLER_CB callback function


## -description


The <b>pfnStateVsSamplerCb</b> function causes the Microsoft Direct3D 10 runtime to refresh the vertex shader stage's bound samplers.


## -parameters




### -param Arg1

*hRuntimeDevice* [in]

A handle to a context for the core Direct3D 10 runtime. This handle is supplied to the driver in a call to the driver's <a href="https://msdn.microsoft.com/c69eedb1-c975-412c-aa9f-cf64a702f937">CreateDevice(D3D10)</a> function. 

### -param Arg2

*Count* [in]

The total number of DDI handles to samplers. The number can be -1, which specifies that <b>pfnStateVsSamplerCb</b> will use its high watermarks to substitute an optimal value (which is typically less than the maximum valid value for <i>Count</i>). However, no non-NULL binding exists in a slot larger than the optimal <i>Count</i> value.

### -param Arg3

*Base* [in]

The beginning of the DDI handles to samplers. 




## -returns



None




## -see-also




<a href="https://msdn.microsoft.com/c69eedb1-c975-412c-aa9f-cf64a702f937">CreateDevice(D3D10)</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff541820">D3D10DDI_CORELAYER_DEVICECALLBACKS</a>
 

 

