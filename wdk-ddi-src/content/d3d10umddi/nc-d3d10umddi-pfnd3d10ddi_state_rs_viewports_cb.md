---
UID: NC:d3d10umddi.PFND3D10DDI_STATE_RS_VIEWPORTS_CB
title: PFND3D10DDI_STATE_RS_VIEWPORTS_CB (d3d10umddi.h)
description: The pfnStateRsViewportsCb function causes the Microsoft Direct3D 10 runtime to refresh the viewport state.
old-location: display\pfnstatersviewportscb.htm
ms.date: 05/10/2018
keywords: ["PFND3D10DDI_STATE_RS_VIEWPORTS_CB callback function"]
ms.keywords: PFND3D10DDI_STATE_RS_VIEWPORTS_CB, PFND3D10DDI_STATE_RS_VIEWPORTS_CB callback, d3d10state_functions_ed84e257-d988-47db-a588-800a7c74ed45.xml, d3d10umddi/pfnStateRsViewportsCb, display.pfnstatersviewportscb, pfnStateRsViewportsCb, pfnStateRsViewportsCb callback function [Display Devices]
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
targetos: Windows
tech.root: display
req.typenames: 
f1_keywords:
 - PFND3D10DDI_STATE_RS_VIEWPORTS_CB
 - d3d10umddi/PFND3D10DDI_STATE_RS_VIEWPORTS_CB
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - d3d10umddi.h
api_name:
 - PFND3D10DDI_STATE_RS_VIEWPORTS_CB
---

# PFND3D10DDI_STATE_RS_VIEWPORTS_CB callback function


## -description

The <b>pfnStateRsViewportsCb</b> function causes the Microsoft Direct3D 10 runtime to refresh the viewport state.

## -parameters

### -param Arg1

*hRuntimeDevice* [in]

A handle to a context for the core Direct3D 10 runtime. This handle is supplied to the driver in a call to the driver's <a href="/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d10ddi_createdevice">CreateDevice(D3D10)</a> function.

## -remarks

The <b>pfnStateRsViewportsCb</b> function calls the user-mode display driver's <a href="/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d10ddi_setviewports">SetViewports</a> function with all of the currently set viewports.

## -see-also

<a href="/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d10ddi_createdevice">CreateDevice(D3D10)</a>



<a href="/windows-hardware/drivers/ddi/d3d10umddi/ns-d3d10umddi-d3d10ddi_corelayer_devicecallbacks">D3D10DDI_CORELAYER_DEVICECALLBACKS</a>



<a href="/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d10ddi_setviewports">SetViewports</a>

