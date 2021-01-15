---
UID: NC:d3d10umddi.PFND3D10DDI_STATE_GS_CONSTBUF_CB
title: PFND3D10DDI_STATE_GS_CONSTBUF_CB (d3d10umddi.h)
description: The pfnStateGsConstBufCb function causes the Microsoft Direct3D 10 runtime to refresh the geometry shader constant buffer state.
old-location: display\pfnstategsconstbufcb.htm
ms.date: 05/10/2018
keywords: ["PFND3D10DDI_STATE_GS_CONSTBUF_CB callback function"]
ms.keywords: PFND3D10DDI_STATE_GS_CONSTBUF_CB, PFND3D10DDI_STATE_GS_CONSTBUF_CB callback, d3d10state_functions_d0994a2d-dd79-490e-b35a-04719bfa1450.xml, d3d10umddi/pfnStateGsConstBufCb, display.pfnstategsconstbufcb, pfnStateGsConstBufCb, pfnStateGsConstBufCb callback function [Display Devices]
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
 - PFND3D10DDI_STATE_GS_CONSTBUF_CB
 - d3d10umddi/PFND3D10DDI_STATE_GS_CONSTBUF_CB
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - d3d10umddi.h
api_name:
 - PFND3D10DDI_STATE_GS_CONSTBUF_CB
---

# PFND3D10DDI_STATE_GS_CONSTBUF_CB callback function


## -description

The <b>pfnStateGsConstBufCb</b> function causes the Microsoft Direct3D 10 runtime to refresh the geometry shader constant buffer state.

## -parameters

### -param Arg1

*hRuntimeDevice* [in]

A handle to a context for the core Direct3D 10 runtime. This handle is supplied to the driver in a call to the driver's <a href="/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d10ddi_createdevice">CreateDevice(D3D10)</a> function.

### -param Arg2

*Count* [in]

The total number of constant buffers. The number can be -1, which specifies that the Direct3D runtime will use its high watermarks to substitute an optimal value (which is typically less than the maximum valid value for <i>Count</i>). However, no non-NULL binding exists in a slot larger than the optimal <i>Count</i> value.

### -param Arg3

*Base* [in]

The beginning constant buffer for which the runtime should refresh state.

## -see-also

<a href="/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d10ddi_createdevice">CreateDevice(D3D10)</a>



<a href="/windows-hardware/drivers/ddi/d3d10umddi/ns-d3d10umddi-d3d10ddi_corelayer_devicecallbacks">D3D10DDI_CORELAYER_DEVICECALLBACKS</a>

