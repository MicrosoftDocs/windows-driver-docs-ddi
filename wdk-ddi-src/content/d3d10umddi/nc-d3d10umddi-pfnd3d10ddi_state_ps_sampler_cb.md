---
UID: NC:d3d10umddi.PFND3D10DDI_STATE_PS_SAMPLER_CB
title: PFND3D10DDI_STATE_PS_SAMPLER_CB (d3d10umddi.h)
description: The pfnStatePsSamplerCb function causes the Microsoft Direct3D 10 runtime to refresh the pixel shader stage's bound samplers.
old-location: display\pfnstatepssamplercb.htm
ms.assetid: 8cf25918-1acf-40b6-be51-2c1afc419f2a
ms.date: 05/10/2018
ms.keywords: PFND3D10DDI_STATE_PS_SAMPLER_CB, PFND3D10DDI_STATE_PS_SAMPLER_CB callback, d3d10state_functions_2e14a132-dd8b-4a78-905e-b2d74d9e669d.xml, d3d10umddi/pfnStatePsSamplerCb, display.pfnstatepssamplercb, pfnStatePsSamplerCb, pfnStatePsSamplerCb callback function [Display Devices]
ms.topic: callback
f1_keywords:
 - "d3d10umddi/pfnStatePsSamplerCb"
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
- pfnStatePsSamplerCb
product:
- Windows
targetos: Windows
tech.root: display
req.typenames: 
---

# PFND3D10DDI_STATE_PS_SAMPLER_CB callback function


## -description


The <b>pfnStatePsSamplerCb</b> function causes the Microsoft Direct3D 10 runtime to refresh the pixel shader stage's bound samplers.


## -parameters




### -param Arg1

*hRuntimeDevice* [in]

A handle to a context for the core Direct3D 10 runtime. This handle is supplied to the driver in a call to the driver's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d10ddi_createdevice">CreateDevice(D3D10)</a> function. 

### -param Arg2

*Count* [in]

The total number of samplers. The number can be -1, which specifies that the Direct3D runtime will use its high watermarks to substitute an optimal value (which is typically less than the maximum valid value for <i>Count</i>). However, no non-NULL binding exists in a slot larger than the optimal <i>Count</i> value.

### -param Arg3

*Base* [in]

The beginning sampler for which the runtime should refresh state. 

## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d10ddi_createdevice">CreateDevice(D3D10)</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/ns-d3d10umddi-d3d10ddi_corelayer_devicecallbacks">D3D10DDI_CORELAYER_DEVICECALLBACKS</a>
 

 

