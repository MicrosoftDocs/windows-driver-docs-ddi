---
UID: NC:d3d10umddi.PFND3D10DDI_SETERROR_CB
title: PFND3D10DDI_SETERROR_CB (d3d10umddi.h)
description: The pfnSetErrorCb function sets the return error code of a user-mode display driver's function.
old-location: display\pfnseterrorcb.htm
ms.date: 05/10/2018
keywords: ["PFND3D10DDI_SETERROR_CB callback function"]
ms.keywords: PFND3D10DDI_SETERROR_CB, PFND3D10DDI_SETERROR_CB callback, d3d10state_functions_1d57cbc9-ec37-47ce-ab4f-71535419375a.xml, d3d10umddi/pfnSetErrorCb, display.pfnseterrorcb, pfnSetErrorCb, pfnSetErrorCb callback function [Display Devices]
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
 - PFND3D10DDI_SETERROR_CB
 - d3d10umddi/PFND3D10DDI_SETERROR_CB
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - d3d10umddi.h
api_name:
 - PFND3D10DDI_SETERROR_CB
---

# PFND3D10DDI_SETERROR_CB callback function


## -description

The <b>pfnSetErrorCb</b> function sets the return error code of a user-mode display driver's function.

## -parameters

### -param Arg1

*hRuntimeDevice* [in]

A handle to a context for the core Microsoft Direct3D 10 runtime. This handle is supplied to the driver in a call to the driver's <a href="/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d10ddi_createdevice">CreateDevice(D3D10)</a> function.

### -param Arg2

*hResult* [in]

An HRESULT value that specifies the error to set for a driver function.

## -remarks

A user-mode display driver can call <b>pfnSetErrorCb</b> many times for each driver invocation. For the driver's functions that do not return status codes, the driver uses <b>pfnSetErrorCb</b> to return error information to the Direct3D runtime.

## -see-also

<a href="/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d10ddi_createdevice">CreateDevice(D3D10)</a>



<a href="/windows-hardware/drivers/ddi/d3d10umddi/ns-d3d10umddi-d3d10ddi_corelayer_devicecallbacks">D3D10DDI_CORELAYER_DEVICECALLBACKS</a>

